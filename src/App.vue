
<template>
  <div id="app">
    <ejs-diagram
      id="diagram"
      :width="width"
      :height="height"
      :nodes="nodes"
      :connectors="connectors"
      :getNodeDefaults="getNodeDefaults"
    ></ejs-diagram>
  </div>
</template>
<script>
import Vue from "vue";
import { DiagramPlugin } from "@syncfusion/ej2-vue-diagrams";

Vue.use(DiagramPlugin);

let nodes = [
  {
    id: "First",
    width: 140,
    height: 50,
    offsetX: 300,
    offsetY: 100,
    annotations: [
      {
        id: "label1",
        content: "First",
      },
    ],
    shape: {
      type: "Flow",
      shape: "Process",
    },
  },
  {
    id: "Second",
    width: 140,
    height: 50,
    offsetX: 300,
    offsetY: 300,
    shape: {
      type: "Flow",
      shape: "Process",
    },
    annotations: [
      {
        content: "Second",
      },
    ],
  },
  {
    id: "Third",
    width: 140,
    height: 50,
    offsetX: 300,
    offsetY: 500,
    shape: {
      type: "Flow",
      shape: "Process",
    },
    annotations: [
      {
        content: "Third",
      },
    ],
  },
];

let connectors = [
  {
    id: "connector1",
    style: {
      strokeColor: "Green",
      fill: "Green",
      strokeWidth: 2,
    },
    targetDecorator: {
      style: {
        fill: "Green",
        strokeColor: "Green",
      },
    },
    sourceID: "First",
    targetID: "Second",
    connectorSpacing: 7,
    type: "Orthogonal",
  },
  {
    id: "connector2",
    style: {
      strokeColor: "Green",
      fill: "Green",
      strokeWidth: 2,
    },
    targetDecorator: {
      style: {
        fill: "Green",
        strokeColor: "Green",
      },
    },
    sourceID: "Second",
    targetID: "Third",
    connectorSpacing: 7,
    type: "Orthogonal",
  },
];
export default {
  name: "app",
  data() {
    return {
      width: "100%",
      height: "750px",
      nodes: nodes,
      connectors: connectors,
      getNodeDefaults: (node) => {
        node.height = 100;
        node.width = 100;
        node.style.fill = "Green";
        node.style.strokeColor = "white";
        return node;
      },
    };
  },
};
</script>
<style>
@import "@syncfusion/ej2-vue-diagrams/styles/material.css";
</style>