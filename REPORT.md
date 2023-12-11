# Graph Neural Networks - Comprehensive Report

## Introduction
In this project, I will first try to understand the theory behind Graphs and their use with Neural Networks. Then, in a second part, I will detail the approach used in order to make Graph Level predictions applied to Molecules Data. Finally, in a third part, I will introduce the work that has been done to implement a Graph Transformer from scratch (*compléter*)

## I - Graph Neural Network Theory

### 1 - What is a Graph ?

A **Graph** can be defined as a Data Structure where elements have nodes, and edges linking nodes between them. 

--> For example, when speaking about molecules, that can be represented with a Graph Structure, the nodes are the atoms of the modecule, and the edges are the chemical bonds linking atoms together.

Graphs are particularly useful to deal with complex interactions between particular entities, and they are widely used with social relations, text and image analysis for example.

Here are a few examples of Graphs that could be used to solve Data Science problematics.

<p align="center">

<div style="display: flex; justify-content: center;">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/1a/Sucrose_molecule.svg/1200px-Sucrose_molecule.svg.png" alt="Image Alt Text" width="250" style="margin-right: 40px;"/>
  <img src="https://ars.els-cdn.com/content/image/1-s2.0-S2352711019302626-gr4.jpg" alt="Image 2" width = "180">
</div>

</p>


<p align="center">

<div style="display: flex; justify-content: center;">
  <img src="https://deeplobe.ai/wp-content/uploads/2023/06/Object-detection-Real-world-applications-and-benefits.png" alt="Image Alt Text" width="200" style="margin-right: 75px;"/>
  <img src="https://gatton.uky.edu/sites/default/files/iStock-networkWEB.png
" alt="Image 2" width = "180>
</div>

</p>

From each of these images, we can deduce a Graph Structure made of Nodes and Edges to link them. For the bottom left image, even if it is not straight forward, we could link the two people by a link of type *Human*, and link the two cars with a *vehicle* link for example.


### 2 - What kind of Predictions ?

Graph Data can be used for 3 particular types of prediction tasks : 

#### *2a - Node Level Predictions* : 

It is possible to predict a missing node label from its relations with other nodes. As a straight forward example, a Carbon Dioxyde Molecule has the following Graph Structure : 

<p align="center">
<img src="https://upload.wikimedia.org/wikipedia/commons/a/a0/Carbon_dioxide_3D_ball.png" alt="Image Alt Text" width="300"/>
</p>



Now imagine that the right hand side atom of this molecule was unknown. Then, by basic Chemistry knowledge, we can say that this atom is an Oxygen atom, as it has a double chemical bond with the Carbon atom next to it. Learning relations between nodes, the type and attributes of edges that connect them can thus help predicting a Node label.

#### *2b - Link Predictions*

Another possible task to perform is to predict if there is a link between two nodes, and also possibly predict the type of link that links them.

This type of task is very useful for social interaction analysis. Imagine we are considering social relationships between a group of people, but we do not know if two people are actually linked by, let us say, a *friendship* edge.

<p align="center">
<img src="https://encrypted-tbn3.gstatic.com/images?q=tbn:ANd9GcQDpsitX6WslVX-xPlkvnOX5Se43i9-hJqA63NXyMfZSRyzrdup" alt="Image Alt Text" width="300"/>
</p>

Then, by analysing the graph as a whole, we can make predictions about whether or not these two people are linked. Indeed, if we see that other people are linked to both of them as friends, we could think that the two people have good chances of being friends as well. 

This type of prediction can have amazing value nowadays with the role that play social media and virtual social interactions in our society.

#### *2c - Graph Level Predictions*

This type of predictions is when you wan to predict a characteristic, or a number for example, by looking at a whole known graph, its interactions and properties. For example, when dealing with Recommendation System, you can find yourslef with a graph like this : 

<p align="center">
<img src="https://miro.medium.com/v2/resize:fit:720/format:webp/1*MVzPPB2RSFNvMsQbzzl0OA.png" alt="Image Alt Text" width="450"/>
</p>

From this clients file represented as a Graph, you can for example decide to send a promotionnal e-mail to these clients based on their preferences.

As such, Graphs can be a valuable Data Structure for many domains, and the potential of predictions has been increasing sharply with the development of Deep Learning algorithms.

### 3 - Neural Network Theory

#### *3a - Data Specificities*