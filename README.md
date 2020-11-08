# Haefner lab page

## Run the page locally using Jekyll

To run locally, follow instruction [here](https://jekyllrb.com/) to install Jekyll then run `jekyll serve` to see in `localhost:4000`. Here is a brief install guidelines.

```bash
gem install jekyll
gem install rouge
jekyll serve
```

## To make minor edits

If you want to add new content, like blogs, posts, publications and lab members, it can all be achieved just editing through the github website. Keep reading. 

## To add new lab members

New lab members can be added into the `_people` directory, with a file name like `firstname_lastname.md`

```
---
name: Computational Ninja
position: gradstudent
avatar: something.jpg
twitter: 
webpage: haefnerlab.gitbhub.io
joined: 2019
---

## Whatever I want to add about me.

```
By default, the file parses the `avatar` photo from the `images/people` directory. So make sure you add your picture in that directory. The following fields are available for the postition in the lab. Choose only one of them (hope they are self explanatory).

`pi|postdoc|gradstudent|researchstaff|undergraduate|visiting|others|alumni`

To remove a lab member (once they graduate, or otherwise), simply remove their `lab-member.md` file from the `_people` directory. 

### What do posts look like

It's very easy to add post. All the posts are located in `_posts` folder. It arrangement is based on
date. Each post can be written in markdown format. You just have to state headers before writing: `title`, `description` and `categories`. `description` will be shown when you share on social media like Facebook or twitter. See the following headers:

**IMPORTANT NOTE:** For the posts to be parsed, add the file with name: `YYYY-MM-DD-Word1-Word2-Word3.md`

``` markdown
---
title: How to add a blog post and other things
description: Tells you how you can add a blog post. 
categories: newblog
header-img: images/image.png
author: Computational Ninja
hidden: True
---

Add content here. 
```

We have categories : `newblog` (for blog posts and publication blog posts), `science` (Description of a scientific idea the lab has been working on), `tuts` (Tutorials for coding practices, editing figures etc.), and `logistics` for information about how lab members can navigate through reimbursement processes, room access etc. 

Coming soon: Adding a username capability to be filled in the `author` field, so it could automatically take you to the author's personal page. 

### How to add posts

- **Directly edit on Github**, you can simply go to `_posts` and click `New file` then put some markdown file e.g. `2016-02-03-post-name.md` and start writing blog post. Github also allows you to preview it so it's nice for people who don't want to clone the repo. 

- **Clone the repository**, kind of the same as directly add post on Github. You just have to clone the repository. Then add new post file, commit and push to the repo.

The changes will take approximately half a minute to render. You can see the new posts or changes on [kordinglab.com](http://kordinglab.github.io/)!

## Add a publication

New Publications can be added to `_data/publications.yml` in the following format:

```
- title: Task-induced neural covariability as a signature of approximate Bayesian learning and inference
  authors: RD Lange, RM Haefner
  date: 2020-09-22
  journal: bioRxiv
  link-to-blog: 2020/09/22/Task-induced-variability
  keywords: Approximate Inference
  link-pdf: 081661v4.full.pdf
  link-journal: https://www.biorxiv.org/content/10.1101/081661v4
  abstract-mini:
```
Add `authors` and `keywords` comma-separated. Make sure to not have a `,` at the end of the last author/ keyword. PDFs can be added to the `pdfs` directory. `link-to-blog` can be used if you plan to write a blog about your publication. In this case add a post as described above and then copy the generated link to here. If you created the post as `YYYY-MM-DD-Word1-Word2-Word3.md`, your link will look like: `YYYY/MM/DD/Word1-Word2-Word3`.

## Add news

New News items can be added into `_data/news.yml` in the following format.
``` markdown
- date: YYYY-MM-DD
  details: This thing happenend
```
The site automatically excludes everything that is over 60 days (2months) so don't worry about removing old news items. Just keep adding new ones on top. There are some symbols that cannot be used directly e.g. `:`, be careful.
