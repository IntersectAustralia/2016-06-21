# workshop-template

This repository is [Software Carpentry](http://software-carpentry.org)'s
template for creating websites for workshops.

1.  Do *not* fork this repository directly on GitHub.
    Instead, please use GitHub's importer following the instructions [below](#creating-a-repository)
    to create a website repository for your workshop.

2.  Please *do your work in your repository's `gh-pages` branch*,
    since that is what is [automatically published as a website by GitHub](https://help.github.com/articles/creating-project-pages-manually/).

3.  Once you are done,
    please **send your repository's URL to the [Software Carpentry administrator](mailto:admin@software-carpentry.org)**.
    We build the [list of workshops on the main website](http://software-carpentry.org/workshops/index.html)
    from the data included in your `index.html` page.
    We can only do that if you [customize][customization] that page correctly
    *and* send us a link to your workshop website.

4.  Please also read
    [the notes on customizing your website][customization] and the [FAQ][faq].
    If you're interested in knowing more about why we do things the way we do,
    please check out the [design notes][design].

5.  If you are teaching Git,
    please [create a separate repository](#setting-up-a-separate-repository-for-learners)
    for your learners to practice in.

6.  If you run into problems,
    or have ideas about how to make this process simpler,
    please [get in touch](#getting-and-giving-help).

## Creating a Repository

1.  Go to [GitHub's importer][importer]. 

2.  Paste the url of this repo as the old repository to clone: https://github.com/swcarpentry/workshop-template

3.  Select the owner for your new repository.
    (This will probably be you, but may instead be an organization you belong to.)

4.  Choose a name for your workshop website repository.
    This name should have the form `YYYY-MM-DD-site`,
    e.g., `2015-07-01-miskatonic`.

5.  Make sure the repository is public.

6.  At this point, you should have a page like this:

    ![](fig/using-github-import.png?raw=true)

    You can now click "Begin Import".
    When the process is done,
    you can click "Continue to repository" to visit your newly-created repository.

**Note:**
some people have had intermittent errors during the import process,
possibly because of the network timing out.
If you experience a problem, please re-try;
if the problem persists,
please [get in touch](#getting-and-giving-help).

## Customizing Your Website

1.  Go into your newly-created repository,
    which will be at `https://github.com/your_username/YYYY-MM-DD-site`.
    For example,
    if `your_username` is `gvwilson`,
    the repository's URL will be `https://github.com/gvwilson/2015-07-01-mistaktonic`.

2.  Edit `index.html` to customize the list of instructors,
    workshop venue, etc. 
    You can do this in the browser by clicking on it in the file view on GitHub
    and then selecting the pencil icon in the menu bar:

    ![](fig/edit-index-file-menu-bar.png?raw=true)
    
    Editing hints are embedded in `index.html`,
    and full instructions are in [_extras/customization.md][customization].

    > Alternatively, you can clone the repository to your desktop,
    > edit `index.html` there,
    > and push your changes back to the repository.
    >
    > ~~~
    > git clone -b gh-pages https://github.com/your_username/YYYY-MM-DD-site
    > ~~~
    >
    > This is needed because the imported repository doesn't have a `master` branch.
    >
    > **Note:** please do all of your work in your repository's `gh-pages` branch,
    > since [GitHub automatically publishes that as a website](https://help.github.com/articles/creating-project-pages-manually/).

3.  Edit `_config.yml` in the same way
    so that `workshop_repo` and `workshop_site`
    are the URLs of your repository and your GitHub Pages website respectively.

    Note: the URL for your website is determined automatically
    based on the URL for your repository.
    If your repository is at `https://github.com/your_username/YYYY-MM-DD-site`,
    its GitHub Pages website is at `http://your_username.github.io/YYYY-MM-DD-site`.

4.  When you are done editing,
    you can view your website:
    if your repository is `https://github.com/your_username/YYYY-MM-DD-site`,
    its website will be `http://your_username.github.io/YYYY-MM-DD-site`.

Full instructions are available in [_extras/customization.md][customization].
This [FAQ][faq] includes a few extra tips
(additions are always welcome)
and these notes on [the background and design][design] of this template may help as well.

That's it.
The following steps are only necessary if you want to run the website locally on your computer.

## Checking Your Changes

1.  To check your changes on your desktop you need some softwares
    described at [Installing Software session](#installing-software).
    This may require some work to set up,
    so feel free to preview by pushing to the website.

2.  For some links to work properly,
    particularly the link to your workshop's Eventbrite registration page,
    you must view `_site/index.html` using an HTTP server.
    If you have Jekyll installed,
    you can do this by running:

    ~~~
    $ jekyll server -d _site
    ~~~

    and going to http://localhost:4000.

## Installing Software

If you want to set up Jekyll
so that you can preview changes on your own machine before pushing them to GitHub,
you must install the software described below.
(Note: Julian Thilo has written instructions for
[installing Jekyll on Windows][jekyll-windows].)

1.  **Ruby**.
    This is included with Linux and Mac OS X;
    the simplest option on Windows is to use [RubyInstaller][ruby-installer].
    You can test your installation by running `ruby --version`.
    For more information,
    see [the Ruby installation guidelines][ruby-install-guide].

2.  **[RubyGems][rubygems]**
    (the package manager for Ruby).
    You can test your installation by running `gem --version`.

3.  **[Jekyll][jekyll]**.
    You can install this by running `gem install jekyll`.

If you want to run `bin/workshop_check.py` (which is invoked by `make workshop-check`)
you will need Jekyll (so that you have its Markdown parser, which is called Kramdown)
and the [PyYAML][pyyaml] module for Python 3.

## Setting Up a Separate Repository for Learners

If you are teaching Git,
you should create a separate repository for learners to use in that lesson.
You should not have them use the workshop website repository because:

*   your workshop website repository contains many files
    that most learners don't need to see during the lesson,
    and

*   you probably don't want to accidentally merge
    a damaging pull request from a novice Git user
    into your workshop's website while you are using it to teach.

You can call this repository whatever you like,
and add whatever content you need to it.

## Getting and Giving Help

We are committed to offering a pleasant setup experience for our learners and organizers.
If you find bugs in our instructions,
or would like to suggest improvements,
please [file an issue][issues]
or [mail us][contact].

[contact]: mailto:admin@software-carpentry.org
[customization]: https://swcarpentry.github.io/workshop-template/customization/
[design]: https://swcarpentry.github.io/workshop-template/design/
[faq]: https://swcarpentry.github.io/workshop-template/faq/
[importer]: http://import.github.com/new
[issues]: https://github.com/swcarpentry/workshop-template/issues
[jekyll]: https://jekyllrb.com/
[jekyll-windows]: http://jekyll-windows.juthilo.com/
[pyyaml]: https://pypi.python.org/pypi/PyYAML
[ruby-install-guide]: https://www.ruby-lang.org/en/downloads/
[ruby-installer]: http://rubyinstaller.org/
[rubygems]: https://rubygems.org/pages/download/
