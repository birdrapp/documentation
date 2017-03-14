---
title: Birdr API Reference

toc_footers:

includes:
  - errors

search: true
---


<h1 id="introduction" class="visible">Introduction</h1>

Welcome to the Birdr API documentation.

# Birds

## Get all birds
<span class="verb get">GET</span> <span class="url">https://api.birdr.co.uk/birds</span>

## Get a specific bird
<span class="verb get">GET</span> <span class="url">https://api.birdr.co.uk/birds/{id}</span>

## Create a new bird

<span class="verb post">POST</span> <span class="url">https://api.birdr.co.uk/birds/{id}</span>

## Delete a bird

<span class="verb delete">DELETE</span> <span class="url">https://api.birdr.co.uk/birds/{id}</span>

# Lists

## Get all lists

<span class="verb get">GET</span> <span class="url">https://api.birdr.co.uk/lists</span>

## Get a specific list

<span class="verb get">GET</span> <span class="url">https://api.birdr.co.uk/lists/{id}</span>

## Create a new list

<span class="verb post">POST</span> <span class="url">https://api.birdr.co.uk/lists</span>

## Delete a list

<span class="verb delete">DELETE</span> <span class="url">https://api.birdr.co.uk/lists/{id}</span>

## List all birds in a list

<span class="verb get">GET</span> <span class="url">https://api.birdr.co.uk/lists/{id}/birds</span>

## Add a bird to the list

<span class="verb post">POST</span> <span class="url">https://api.birdr.co.uk/lists/{id}/birds</span>

## Remove a bird from the list

<span class="verb delete">DELETE</span> <span class="url">https://api.birdr.co.uk/lists/{list_id}/birds/{bird_id}</span>
