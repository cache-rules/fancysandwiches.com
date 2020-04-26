# Setup

1. Clone this repo somewhere on your machine.
2. Install Python
3. [Install Lektor](https://www.getlektor.com/docs/installation/)
    - Lektor requires imagemagick which can be installed via `brew install imagemagick` on OS X.
4. To run the dev server run `lektor serve`, which will start a web server at
`http://127.0.0.1:5000/` where you can preview the site, and access the admin panel.

# Adding content

Adding content in Lektor is pretty easy, for the most part you need to do two things:
* Create a folder somewhere in the `/content` folder, where the name of hte folder will be the
desired URL slug (for example `content/hello-world/` will become
`www.fancysandwiches.com/hello-word/`).
* Create a `contents.lr` file in the folder you just created, this will host all of the text content
and other settings for the page. A `contents.lr` file is is a key-value file, where each key and
value is separated by `---`, which allows values to be multiline.
* If you want to use a UI to do this work for you, you can start the dev server and navigate to the
admin panel [http://localhost:5000/admin/root/edit](http://localhost:5000/admin/root/edit)
* For additional info see the [Lektor Content Docs](https://www.getlektor.com/docs/content/)

## Adding a page
1. Create a new folder in `content/`, where the folder name is the desired URL of your post
(for example `content/blog/hello-world` will be come `www.fancysandwiches.com/hello-world`)
2. Add a `contents.lr` file with the following contents:
    ```
    title: Your Title Here (Can be different than folder name)
    ---
    body:
    # The Contents of the page
    All of this supports [Markdown](https://www.markdownguide.org/basic-syntax)
    ```

## Adding a blog post
1. Create a new folder in `content/blog/`, where the folder name is the desired URL of your post
(for example `content/blog/hello-world` will be come `www.fancysandwiches.com/blog/hello-world`)
2. Add a `contents.lr` file with the following contents:
    ```
    title: Your Blog Post Title
    ---
    author: Your Name
    ---
    pub_date: 2020-01-01
    ---
    twitter_handle: your_twitter_handle_without_@_prefix
    ---
    draft: true
    ---
    preview: Preview text you want to show on blog list page, can be markdown
    ---
    body: The content of your blog post, can be markdown.
    ```
    - Note: while your post is a draft (via `draft: true`) it won't show up in the blog list, but
    you can still navigate to it by manually typing in the URL. This is useful if you want to share
    the post with someone before making it public. When you're ready to publish set `draft: false`.
3. Adding pictures (optional)
    1. Add the pictures you want to attach to the same folder as your content.lr file
    2. In your body or preview text add the image with the Markdown picture syntax, for example:
    `![Image alt text for screen readers](your_image_name.jpg "Text to show on hover")`

# Deploying
1. Run `lektor build`
2. Run `lektor deploy`
3. Check www.fancysandwiches.com for your fresh content or changes