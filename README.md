# Readable Languages
A small publishing house for language learners.

# Building the procject
##  Install Ruby
Go to: https://rubyinstaller.org
Download the Ruby+Devkit version (for example: Ruby 3.2.x (x64)) – choose the one labeled "with Devkit".
Run the installer:
During setup, make sure you check the box to add Ruby to the PATH.
After installation, leave the checkbox ticked for ridk install, then follow prompts to install MSYS2 components.

## Install Jekyll dependencies
gem install bundler

## Build and preview the site
bundle install
bundle exec jekyll serve
