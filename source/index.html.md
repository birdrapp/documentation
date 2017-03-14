---
title: Birdr API Reference

toc_footers:

includes:
  - errors

language_tabs:
  - plaintext: HTTP
  - shell: Shell

search: true
---


<h1 id="introduction" class="visible">Introduction</h1>

Welcome to the Birdr API.

This documentation is intended to aid any developers wishing to build an application using the Birdr API.

For each endpoint in this document you will find sample snippets you can use, in two available formats:

 * HTTP request
 * Curl command

# Birds

## Get all birds

```plaintext
GET https://api.birdr.co.uk/birds?
  page=PAGE&
  perPage=PER_PAGE&
  q=QUERY&
  scientificName=SCIENTIFIC_NAME
```

> Sample response:

```json
{
  "page": 1,
  "perPage": 20,
  "total": 31148,
  "links": {
    "next": "https://api.birdr.co.uk/birds?page=2&perPage=20",
    "previous": null
  },
  "data": [
    {
      "id": "6950a3b6-0756-11e7-891a-1b6429a03d29",
      "commonName": "Common Ostrich",
      "scientificName": "Struthio camelus",
      "familyName": "Ostriches",
      "family": "Struthionidae",
      "order": "Struthioniformes",
      "sort": 1,
      "speciesId": null,
      "createdAt": "2017-03-12T19:02:17.354Z",
      "updatedAt": "2017-03-12T19:02:17.354Z",
      "subspecies": null,
      "links": {
        "self": "https://api.birdr.co.uk/birds/6950a3b6-0756-11e7-891a-1b6429a03d29"
      }
    }
  ]
}
```

<span class="verb get">GET</span> <span class="url">https://api.birdr.co.uk/birds</span>

Returns a paginated list of all birds in the API.

### Request Parameters

Parameter | Description
----------|------------
`page` | The `page` number of results. Default: 1.
`perPage` | The number of results to return per page. Default: 20.
`q` | Use this to search for specific birds. **This is a fuzzy match on the birds common name.**
`scientificName` | Filters birds based on their scientific name. **This is an exact match only filter.**

## Get a specific bird
```plaintext
GET https://api.birdr.co.uk/birds/6950a3b6-0756-11e7-891a-1b6429a03d29
```

```shell
curl https://api.birdr.co.uk/birds/6950a3b6-0756-11e7-891a-1b6429a03d29
```

> Sample response:

```json
{
  "id": "6950a3b6-0756-11e7-891a-1b6429a03d29",
  "commonName": "Common Ostrich",
  "scientificName": "Struthio camelus",
  "familyName": "Ostriches",
  "family": "Struthionidae",
  "order": "Struthioniformes",
  "sort": 1,
  "speciesId": null,
  "createdAt": "2017-03-12T19:02:17.354Z",
  "updatedAt": "2017-03-12T19:02:17.354Z",
  "subspecies": null,
  "links": {
    "self": "https://api.birdr.co.uk/birds/6950a3b6-0756-11e7-891a-1b6429a03d29"
  }
}
```

<span class="verb get">GET</span> <span class="url">https://api.birdr.co.uk/birds/{id}</span>

Returns a specific bird from the API.

### Request Parameters

Parameter | Description
----------|------------
`id` - **Required**  | The unique identifier of the bird you wish to retrieve.

## Create a new bird
```plaintext
POST https://api.birdr.co.uk/birds
{
  "commonName": "Common Ostrich",
  "scientificName": "Struthio camelus",
  "familyName": "Ostriches",
  "family": "Struthionidae",
  "order": "Struthioniformes",
  "sort": 1
}
```

```shell
curl --request POST \
  --url 'https://api.birdr.co.uk/birds'
  --header 'Content-Type: application/json'
  --data '{"commonName": "Common Ostrich", "scientificName": "Struthio camelus", "familyName": "Ostriches", "family": "Struthionidae", "order": "Struthioniformes", "sort": 1}'
```

> Sample response:

```json
{
  "id": "6950a3b6-0756-11e7-891a-1b6429a03d29",
  "commonName": "Common Ostrich",
  "scientificName": "Struthio camelus",
  "familyName": "Ostriches",
  "family": "Struthionidae",
  "order": "Struthioniformes",
  "sort": 1,
  "speciesId": null,
  "createdAt": "2017-03-12T19:02:17.354Z",
  "updatedAt": "2017-03-12T19:02:17.354Z",
  "subspecies": null,
  "links": {
    "self": "https://api.birdr.co.uk/birds/6950a3b6-0756-11e7-891a-1b6429a03d29"
  }
}
```
<span class="verb post">POST</span> <span class="url">https://api.birdr.co.uk/birds</span>

Creates a new bird.

### Request Parameters

Parameter | Description
----------|------------
`commonName`<br>**Required** | The common name of the bird. Typically this is the internationally recognised name, rather than a local or regional alternative.
`scientificName`<br>**Required** | The scientific name of the bird.
`familyName`<br>**Required** | The English name of the scientific family of the bird.
`family`<br>**Required** | The scientific family this bird belongs to.
`order`<br>**Required** | The scientific order this bird belongs to.
`sort`<br>**Required** | An integer value representing where this bird should appear in the order of birds.

### Response

The API will return the newly created bird in the response - including a newly generated ID.

## Delete a bird
```plaintext
DELETE https://api.birdr.co.uk/birds/6950a3b6-0756-11e7-891a-1b6429a03d29
```

```shell
curl --request DELETE --url 'https://api.birdr.co.uk/birds/6950a3b6-0756-11e7-891a-1b6429a03d29'
```
<span class="verb delete">DELETE</span> <span class="url">https://api.birdr.co.uk/birds/{id}</span>

Removes a bird from the API.

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
