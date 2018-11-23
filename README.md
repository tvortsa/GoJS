GoJS, это JavaScript библиотека для HTML диаграм
================================================

<img align="right" height="150" src="https://www.nwoods.com/images/go.png">

[GoJS](https://gojs.net) это JavaScript и TypeScript библиотека для создания и манипуляций диаграммами, чартами, и графиками.

![release](https://img.shields.io/github/release/NorthwoodsSoftware/GoJS.svg)
![open issues](https://img.shields.io/github/issues-raw/NorthwoodsSoftware/GoJS.svg)
![last commit](https://img.shields.io/github/last-commit/NorthwoodsSoftware/GoJS.svg)
![downloads](https://img.shields.io/npm/dw/gojs.svg)
[![Twitter Follow](https://img.shields.io/twitter/follow/NorthwoodsGo.svg?style=social&label=Follow)](https://twitter.com/NorthwoodsGo)

[See GoJS Samples](https://gojs.net/latest/samples)

[Get Started with GoJS](https://gojs.net/latest/learn)


GoJS представляет собой гибкую библиотеку, которая может использоваться для создания нескольких различных интерактивных диаграмм, включая визуализацию данных, инструменты рисования и графические редакторы. Вот пример [flowchart](https://gojs.net/latest/samples/flowchart.html), [org chart](https://gojs.net/latest/samples/orgChartEditor.html), [business process BPMN](https://gojs.net/latest/extensions/BPMN.html), [swimlanes](https://gojs.net/latest/samples/swimlanes.html), [timelines](https://gojs.net/latest/samples/timeline.html), [state charts](https://gojs.net/latest/samples/statechart.html), [kanban](https://gojs.net/latest/samples/kanban.html), [network](https://gojs.net/latest/samples/network.html), [mindmap](https://gojs.net/latest/samples/mindMap.html), [sankey](https://gojs.net/latest/samples/sankey.html), [family trees](https://gojs.net/latest/samples/familyTree.html) and [genogram charts](https://gojs.net/latest/samples/genogram.html), [fishbone diagrams](https://gojs.net/latest/extensions/Fishbone.html), [floor plans](https://gojs.net/latest/projects/floorplanner/FloorPlanner.html), [UML](https://gojs.net/latest/samples/umlClass.html), [decision trees](https://gojs.net/latest/samples/decisionTree.html), [pert charts](https://gojs.net/latest/samples/PERT.html), [Gantt](https://gojs.net/latest/samples/gantt.html), and [hundreds more](https://gojs.net/latest/samples/index.html). GoJS includes a number of включает в себя ряд встроенных макетов, включая компоновку дерева, направленную направленность, радиальную и многоуровневую схему орфографии, а также ряд примеров пользовательского макета.

GoJS рендерится в элемент HTML5 Canvas (с экспортом в SVG или изображение). GoJS можно запускать в web браузере, или на стороне сервера в [Node](https://nodejs.org/en/) или [Puppeteer](https://github.com/GoogleChrome/puppeteer). GoJS Диаграммы запечены в Models, которые храняться и загружаются обычно как JSON.

[<img src="https://raw.githubusercontent.com/NorthwoodsSoftware/GoJS/master/.github/github-970x354.png">](https://gojs.net/latest/samples/index.html)

Узнайте больше о GoJS [gojs.net](https://gojs.net)

Этот репозиторий содержит как библиотеку, так и источники для всех образцов, расширений и документации.
Вы можете использовать реппозиторий GitHub [search through all of the sources](https://github.com/NorthwoodsSoftware/GoJS-Samples/search?q=setDataProperty&type=Code).

<h2>Минимальный пример</h2>

Graphs создаются путем создания одного или нескольких шаблонов, с требуемыми свойствами привязки данных и добавления данных модели.

```html
<script src="go.js"></script>

<script id="code">
  function init() {
    var $ = go.GraphObject.make;  // for conciseness in defining templates

    var myDiagram = $(go.Diagram, "myDiagramDiv",  // create a Diagram for the DIV HTML element
                  {
                    // enable undo & redo
                    "undoManager.isEnabled": true
                  });

    // define a simple Node template
    myDiagram.nodeTemplate =
      $(go.Node, "Auto",  // the Shape will go around the TextBlock
        $(go.Shape, "RoundedRectangle", { strokeWidth: 0, fill: "white" },
          // Shape.fill is bound to Node.data.color
          new go.Binding("fill", "color")),
        $(go.TextBlock,
          { margin: 8 },  // some room around the text
          // TextBlock.text is bound to Node.data.key
          new go.Binding("text", "key"))
      );

    // but use the default Link template, by not setting Diagram.linkTemplate

    // create the model data that will be represented by Nodes and Links
    myDiagram.model = new go.GraphLinksModel(
    [
      { key: "Alpha", color: "lightblue" },
      { key: "Beta", color: "orange" },
      { key: "Gamma", color: "lightgreen" },
      { key: "Delta", color: "pink" }
    ],
    [
      { from: "Alpha", to: "Beta" },
      { from: "Alpha", to: "Gamma" },
      { from: "Beta", to: "Beta" },
      { from: "Gamma", to: "Delta" },
      { from: "Delta", to: "Alpha" }
    ]);
  }
</script>
```

Creates this graph. The user can now click on nodes or links to select them, copy-and-paste them, drag them, delete them, scroll, pan, and zoom, with a mouse or with fingers.

[<img width="200" height="200" src="https://gojs.net/latest/assets/images/screenshots/minimal.png">](https://gojs.net/latest/samples/minimal.html)

*Click the image to see the interactive GoJS Diagram*


<h2>Support</h2>

Northwoods Software offers a month of free developer-to-developer support for GoJS to help you get started on your project.

Read and search the official <a href="https://forum.nwoods.com/c/gojs">GoJS forum</a> for any topics related to your questions.

Posting in the forum is the fastest and most effective way of obtaining support for any GoJS related inquiries.
Please register for support at Northwoods Software's <a href="https://www.nwoods.com/products/register.html">registration form</a> before posting in the forum.

For any nontechnical questions about GoJS, such as about sales or licensing,
please visit Northwoods Software's <a href="https://www.nwoods.com/contact.html">contact form</a>.


<h2>License</h2>

The GoJS <a href="https://gojs.net/latest/license.html">software license</a>.


Copyright (c) Northwoods Software Corporation
