# HentaiAPI

[![Build status](https://ci.appveyor.com/api/projects/status/9u2xoxn47irix7gp?svg=true)](https://ci.appveyor.com/project/andy840119/nhentaiapi)
[![CodeFactor](https://www.codefactor.io/repository/github/andy840119/nhentaiapi/badge)](https://www.codefactor.io/repository/github/andy840119/nhentaiapi)
[![NuGet](https://img.shields.io/nuget/v/NHentaiAPI.svg)](https://www.nuget.org/packages/NHentaiAPI)
[![NuGet](https://img.shields.io/nuget/dt/NHentaiAPI.svg)](https://www.nuget.org/packages/NHentaiAPI)
[![NuGet](https://img.shields.io/badge/月子我婆-passed-ff69b4.svg)](https://github.com/andy840119/NHentaiAPI)

A (full)  nHentai API implementation for .NET

NOTE : Because N-Hentai Close its api temporarily. This package might not work normally.
If N-Hentai re-open the api or change the api format, please throw a issue to let me know :)

## This package can get

Search:

1. Home page search result

2. Search result by `keyword`

3. Search result by `tag`, can be sort by popular

Book detail:

1. Book detail

2. Related book

Picture:

1. Page picture (preview picture, thumbnail and origin picture)
2. Cover picture (preview picture and thumbnail)

## Demo

Search book:

```CSharp
//generate client
var client = new NHentaiClient();

//https://nhentai.net/api/galleries/search?query=school%20swimsuit%20loli%20full%20color&page=2
var result = await client.GetSearchPageListAsync("school swimsuit loli full color",2);
```

Get book detail:

```CSharp
//generate client
var client = new NHentaiClient();

//get book no 123
var book = await client.GetBookAsync(123);

```

Get cover and image:

```CSharp
//get book no 123
var book = await client.GetBookAsync(123);

//https://i.nhentai.net/galleries/635/1.jpg
byte[] picture = await client.GetPictureAsync(book, 1);

//https://i.nhentai.net/galleries/635/1.jpg
byte[] cover = await client.GetBigCoverPictureAsync(book);
```

