---
layout: post
title:  "Experiment with Jekyll for building this site."
date:   2020-02-23 17:19:43 +0530
categories: jekyll update
---
This my first post. Thought that I'll dedicate this post to the framework that helped me build this site - Jekyll. I had heard about Jekyll and decided to give it a shot over the weekend.

Setup -
First step to get started with Jekyll is to get the development environment right. An important thing to keep in mind while setting up the environment is whenever the system throws a permission denied error REFRAIN from using sudo (control that itchy instinct of yours 😛). Messing with anything related to ruby at a global level may create a havoc (in MacOS). The installation steps are well documented already by [jekyll][jekyll_installation]. Just documenting what I went through.

1. Ruby installation - regardless of what Ruby version is installed in your system, the recommended practice is to manage ruby versions using `rbenv` - [installation guide][rbenv_site].
2. Once `rbenv` is installed, make sure you run rbenv doctor to make sure the installation was successful.
3. Run `rbenv init` and `rbenv versions`. Note that the default ruby version would be marked as system.
4. Install the required ruby version by running `rbenv install X.X.X`. This step takes time. Have patience even though the process looks like its stuck forever. If you are a person who lacks patience and likes to incremental progress, run the command with verbose option - `rbenv install X.X.X -v`.
5. Navigate to your project directory and `rbenv local X.X.X`. You can also choose to set the version globally by running `rbenv global X.X.X`. I prefer restricting the scope, hence used local.
6. Run `ruby -v` to ensure that correct ruby version is being used for the project.
7. If the version doesn't match the intended one, then run `which ruby`. It should point to the rbenv shims. [e.g. /Users/xyz/.rbenv/shims/ruby]. That's how rbenv manages different versions of ruby. If this doesn't show up then refer to this [question][ruby_path_issue].
8. Once ruby is sorted, install bundler and jekyll. I would recommend perfoming a user install rather than installing globally. `gem install --user-install bundler jekyll`
9. For getting your sample Jekyll site started either go through the [instructions][gh_pages_setup] by github or simply run `jekyll new myblog` to create a sample project. Run `bundle exec jekyll serve` to spawns the server on port 4000 [localhost].
10. Headover to the Gemfile in the directory and edit the file as the instructions provided there in order to make it compatible with github pages. (uncomment `gem "github-pages", group: :jekyll_plugins` and comment jekyll gem line.)
11. Once this is done, run `bundle install` followed by `bundle exec jekyll serve`. If you face any conflict related error, delete the `Gemfile.lock` file and run both the commands.

[rbenv_site]: https://github.com/rbenv/rbenv#installation
[jekyll_installation]: https://jekyllrb.com/docs/installation/
[gh_pages_setup]: https://help.github.com/en/github/working-with-github-pages/creating-a-github-pages-site-with-jekyll
[locall_host]: http://localhost:4000
[ruby_path_issue]: [https://stackoverflow.com/questions/10940736/rbenv-not-changing-ruby-version]
