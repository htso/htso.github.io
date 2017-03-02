---
layout: default
title:  "How to hack the package dependency error in R"
date:   2016-12-06 12:34:08-0700
categories: R_hacking
---

{% include post-title.html %}

You want to install a package, but R complains that it doesn't like the version of R you got. The error message read something like this,

`ERROR: this R is version 3.2.1, package 'XYZ' requires R >=  3.2.2`

Typically, all you need to do is to upgrade your current version of R. But there are times when this is not desirable, or not even possilbe. Here is a hack you can try.

WARNING : There's usually a good reason a package depends on a particular version of R. So if yours is way out of line of currency, this may not work. So be warned! 

First, go to CRAN and download the source of the package, which is typically a zipped file with extension `.tar.gz`. For example, the source file for the package `ModelMetrics` is `ModelMetrics_1.1.0.tar.gz`.

Uncompress it into a local directory. In most platforms (Windows, linux), it's just a matter of double clicking it and an unzip app would open it in a window. 

In the top level of the folder, you should see DESCRIPTION, a text file that you can open with any text editor. Open it and you will find a line 

`Depends: R (>= 3.2.2)`

Now, change the version to your current version 3.2.1. Save it. And install this local copy of the package. In R console, type

<pre class="terminal"><code>install.packages("/local/path/to/ThePackage", repo=NULL, type="source")</code></pre>


Voila! The dependency error should go away and you should be able to complete the install.


