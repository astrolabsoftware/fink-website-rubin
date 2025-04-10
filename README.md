# Fink collaboration website

## Edition

### New post

Create a new folder under `content/post`, with the date of the post and a meaningful set of words. Inside this folder, add a markdown file called `index.md`, and add your post. The header of the file must contain at least three entries:

```yaml
title: # the title of your post
date: # YYYY-MM-DD
cardimage: # an image to be shown in the gallery of posts
```

Note that the image for the card must be stored under `assets/` at the root of the repository. If you want to display images in your post, create a folder under `content/post/<your_folder_name>/images` and put images there. Then in your post, display images using:

```md
![my image](images/your_image_name.png)
```

### Layout

The layout components are from the qubt Hugo theme. In case you want to override them, just place them under `layout/`.

## Build

Make sure you have Hugo Extended Edition 0.122.0 or later and Go 1.23.3 or later installed on your local machine. Read the instructions [here](https://gohugo.io/installation/). Then you can access a local version of the website by executing

```bash
hugo server
```

Then navigate to `localhost:1313`

---

## Configuration

See the [wiki](https://github.com/chrede88/qubt/wiki) for all info about configuration.

---

## Deployment

The site is simply deployed using GitHub pages.

---

## Update the Theme Version

The theme version used to build the site is defined in `go.mod` file.

The best practice is to update to released and tested versions. To update to a specific version execute the following command in a terminal/commandline (at the root path of your site repo):

```shell
  hugo mod get github.com/Chrede88/qubt@vX.Y.Z
```
Replace X,Y & Z with the corresponding version numbers. You can find the releases [here](https://github.com/chrede88/qubt/releases). Please check if any breaking changes are listed under the release you want to update to, before proceeding.

---
