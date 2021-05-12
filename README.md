# add-repo

## About:

add-repo was made so that you don't have to run `echo "deb [trusted=yes] repourl ./" | sudo tee -a /etc/apt/sources.list > /dev/null` all the time to add a repo to apt.
With add-repo all you have to do is ```add-repo --repo repourl```, and that`s it! No more messing with the apt files!

add-repo will handle all of that for you!
add-repo will make a backup of your `/etc/apt/sources.list` file
and check if the repo has already been added, if so it will not add the repo,
or if the repo has `not` been added it will add the repo to your system.

## Install

To install add-repo run ```wget -O - https://raw.githubusercontent.com/oxmc/add-repo/main/install | bash```.

## Uninstall

To uninstall add-repo run ```add-repo --uninstall-all``` to remove it completly, or if you want to keep your added repos run ```add-repo --uninstall-keeprepos```.

## Commands:

To list all commands run ```add-repo --help``` or ```add-repo -h```.

# Create repo

## Step 1

To create a repo for add-repo run ```add-repo --create-repo``` or ```add-repo -cr```,
after you have made your `add-repo config file` you need a website to host the file, i use githubpages but any http or https server will work.

## Step 2

Make a directory named apt in your website, in that directory change the name of your `add-repo config file` from `reponame-name` to `name`.
After that upload your `add-repo config file` to the website in the `apt` directory.

## Done!

That's all you need to do!
to test it run ```add-repo --repo yoursitename/apt/name```, and wait for it to finish...
Done! You hve successfully made a add-repo repo!

# FAQ

`How long did it take to make this?`

It took about 2 days to make this.

`I am getting an error 'Unable to run sudo apt-get update!'`

This either means that a: You are not able to run `sudo apt-get update`, or b: The repo url does not have a Packages.gz file.
