---
title: Why I Learn Code
subtitle: Who, What, When, Where, WHY?, How, To What Extent
category:
  - About Awake
author: Blake
date: 2021-5-02T10:10:10.800Z
featureImage: /uploads/CIV1.PNG
---
I have been learning about code for so long. I have spent so much money on it. I can remember sitting in public librarys in Brookline, Cambridge and at home trying to pick up concepts. It just takes so long. But in the last couple years I have been learning and focusing on Javascript. This has focused me and giving me a hugely high goal to get to. After paying for code services that I didnt use, I am now buying books and using free services and videos to learn JS. Oddly this has worked somewhat better. I am now really thinking that in the future I can make Civ1 as a video game, completly in JavaScript.  This really excites me as I want to play it on my phone and anywhere. I also want to improve it and and add features that I have always wanted. This is making me more excited to learn JS and I think is a great goal to have. It will also make me feel like I am accomplishing a life long goal to remake the island civilization of Enzo which I still think about to this day almost 25 plus years later. 

| Question | Description                                          | Type   | Default           |
| -------- | ---------------------------------------------------- | ------ | ----------------- |
| Who   | how many resources to displayed per row              | Number | 3                 |
|  What  | total number of resources to display                 | Number | all (lazy loaded) |
| When | for posts filters posts only in supplied category(s) | Array  | \[]               |
| Where | the resource to be retrieved and displayed           | String | Required          |

There are 2 simple wrappers built around the `ResourceGrid` for easily displaying a categories grid or a posts grid, easily enough they are `CategoriesGrid` and `PostsGrid`.

## Examples
```
<--! All posts in grid with 3 per row lazy loaded until no more-->
<posts-grid />

<--! 3 posts in grid in single row -->
<posts-grid :number="3" />

<--! 3 posts in grid in single row in category-1 (exactly how related posts at end of single post is accomplished) -->
<posts-grid :number="3" :category="['category-1']" />

<--! All categories in grid with 3 per row lazy loaded until no more-->
<categories-grid />

<--! etc -->
```
