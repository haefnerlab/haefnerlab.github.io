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

### Add posts

It's very easy to add post. All the posts are located in `_posts` folder. It arrangement is based on
date. Each post can be written in markdown format. You just have to state headers before writing: `title`, `description` and `categories`. `description` will be shown when you share on social media like Facebook or twitter. See the following headers:

``` markdown
---
title: Summer School in Computational Sensory-Motor Neuroscience (CoSMo)
description: all links to CoSMo summer school in computational neuroscience materials
categories: scientists
---
```

We have 4 categories: `scientists`, `students`, `discussion`, `blog` you can choose and this will be rendered to different location.

### How to add posts

- **Directly edit on Github**, you can simply go to `_posts` and click `New file` then put some markdown file e.g. `2016-02-03-post-name.md` and start writing blog post. Github also allows you to preview it so it's nice for people who don't want to clone the repo. 

- **Clone the repository**, kind of the same as directly add post on Github. You just have to clone the repository. Then add new post file, commit and push to the repo.

The changes will take approximately half a minute to render. You can see the new posts or changes on [kordinglab.com](http://kordinglab.github.io/)!

## Add news

New News items can be added into `_data/news.yml` in the following format.
``` markdown
- date: YYYY-MM-DD
  details: This thing happenend
```
The site automatically excludes everything that is over 60 days (2months) so don't worry about removing old news items. Just keep adding new ones on top. There are some symbols that cannot be used directly e.g. `:`, be careful.
