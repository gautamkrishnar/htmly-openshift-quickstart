# Htmly on openshift

HTMLy is an open source Databaseless Blogging Platform or Flat-File Blog prioritizes simplicity and speed written in PHP. HTMLy can be referred to as Flat-File CMS either since it will also manage your content.

HTMLy uses a unique algorithm to find or list any content based on date, category, tag, or author, and the performance will remain fast even if we have thousands of posts and hundreds of tags.

More information can be found at: https://www.htmly.com/

### Install with one click


Create an account at http://openshift.redhat.com/

[![Click to install OpenShift](http://launch-shifter.rhcloud.com/launch/light/Click to install.svg)](https://openshift.redhat.com/app/console/application_type/custom?&cartridges[]=php-5.4&initial_git_url=https://github.com/gautamkrishnar/htmly-openshift-quickstart)

### How to use
After installing you can login to admin console(still in beta) by pointing your browser to: http://grav-yourdomain.rhcloud.com/install.php to setup your instance of htmly

If you are experiencing any problems, please don't forget to open a [new issue](https://github.com/gautamkrishnar/htmly-openshift-quickstart/issues/new) in this repository.

### Installing via the command line


Create a PHP application :

	rhc app create htmly php-5.4

You can also use any other custom name instead of 'htmly'. Remember to use that app name in the next command

Add this upstream htmly quickstart repo

	cd htmly
	rm php/index.php
	git remote add upstream -m master git://github.com/gautamkrishnar/htmly-openshift-quickstart.git
	git pull -s recursive -X theirs upstream master

Push the repo upstream to OpenShift

	git push        

Head to your application at:

	http://grav-$yourdomain.rhcloud.com

To give your new Grav site a web address of its own, add your desired alias:

	rhc app add-alias -a htmly --alias "$whatever.$mydomain.com"

Then add a cname entry in your domain's dns configuration pointing your alias to $whatever-$yourdomain.rhcloud.com.

### Spread the word
Liked using Grav in openshift! Don't forget to spread the word by starring this repo.
