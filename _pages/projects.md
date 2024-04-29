---
title: Projects
layout: collection
permalink: /projects/
collection: projects
# entries_layout: grid
classes: wide
sort_by: order
---

<!-- 
<style>
#digitalStack rect {
    transition: all 0.3s ease;
}

#digitalStack rect.hovered {
    transform: scale(1.1); /* Slightly enlarges the layer */
    fill: orange; /* Changes color to indicate hover */
}

#projectDetails {
    padding: 20px; 
    border: 1px solid black; 
    margin-top: 20px;
}

/* Additional styling for the SVG and its border */
svg {
    border: 1px solid #ccc;
    margin-top: 20px;
}
</style>

<script src="https://d3js.org/d3.v7.min.js"></script>
<div id="graph"></div>

<script>
// Example data for nodes and links
var nodes = [
    {id: "Project A", group: 1},
    {id: "Project B", group: 1},
    {id: "Project C", group: 2},
    // Add more projects
];

var links = [
    {source: "Project A", target: "Project B"},
    {source: "Project B", target: "Project C"},
    // Define connections between projects
];

var width = 800, height = 600;

// Append SVG to the graph container and add zoom functionality
var svg = d3.select("#graph").append("svg")
    .attr("width", width)
    .attr("height", height)
    .call(d3.zoom().on("zoom", function (event) {
        container.attr("transform", event.transform);
    }))
    .append("g");

var container = svg.append("g");

// Simulation setup with forces
var simulation = d3.forceSimulation(nodes)
    .force("link", d3.forceLink(links).id(d => d.id).distance(100)) // Adjust link distance
    .force("charge", d3.forceManyBody().strength(-400)) // Adjust repulsive force strength
    .force("center", d3.forceCenter(width / 2, height / 2))
    .force("collide", d3.forceCollide().radius(50)); // Prevent node overlap

// Draw lines for links in the container group
var link = container.append("g")
    .attr("class", "links")
    .selectAll("line")
    .data(links)
    .enter().append("line")
    .attr("stroke-width", 2);

// Draw circles for nodes in the container group
var node = container.append("g")
    .attr("class", "nodes")
    .selectAll("circle")
    .data(nodes)
    .enter().append("circle")
    .attr("r", 5)
    .on("mouseover", function() { d3.select(this).transition().attr("r", 10); })
    .on("mouseout", function() { d3.select(this).transition().attr("r", 5); });

// Add draggable and zoomable behavior to nodes
node.call(d3.drag()
    .on("start", dragstarted)
    .on("drag", dragged)
    .on("end", dragended));

// Add labels in the container group
var labels = container.append("g")
    .attr("class", "labels")
    .selectAll("text")
    .data(nodes)
    .enter().append("text")
    .text(function(d) { return d.id; })
    .attr("x", 8)
    .attr("y", "0.31em");

// Update positions within the container
simulation.on("tick", () => {
    link
        .attr("x1", d => d.source.x)
        .attr("y1", d => d.source.y)
        .attr("x2", d => d.target.x)
        .attr("y2", d => d.target.y);

    node
        .attr("cx", d => d.x)
        .attr("cy", d => d.y);

    labels
        .attr("x", d => d.x)
        .attr("y", d => d.y);
});

// Drag and zoom functions
function dragstarted(event) {
    if (!event.active) simulation.alphaTarget(0.3).restart();
    event.subject.fx = event.subject.x;
    event.subject.fy = event.subject.y;
}

function dragged(event) {
    event.subject.fx = event.x;
    event.subject.fy = event.y;
}

function dragended(event) {
    if (!event.active) simulation.alphaTarget(0);
    event.subject.fx = null;
    event.subject.fy = null;
}

</script> -->
