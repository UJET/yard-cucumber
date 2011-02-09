Cucumber-In-The-YARD (CITY): A Requirements Documentation Tool
====================================

Synopsis
--------

Cucumber-In-The-Yard is a YARD extension that processes Cucumber features,
scenarios, steps, tags, step definitions, and even transforms to provide
documentation similar to what you expect to how YARD displays classes, methods
and constants.This tools bridges the gap of having feature files found in
your source code and true documentation that your team, product owners and
stakeholders can use.

Examples
--------

I have created a trivial, example project to help provide a quick 
visualization of the resulting documentation. I encourage you to look at it as 
an example and see if it would assist your project from a multitude of 
perspectives: as the project's core developer; another developer or a new 
developer; quality assurance engineer; or product owner/stakeholder.

The implemented example has been deployed at [http://recursivegames.com/cukes/](http://recursivegames.com/cukes/).

**1. View Features and Scenarios** [example](http://recursivegames.com/cukes/requirements/)

**2. Search through [features, scenarios](http://recursivegames.com/cukes/feature_list.html), and [tags](http://recursivegames.com/cukes/tag_list.html)**

**3. Dynamic Tag Unions and Intersections** [example](http://recursivegames.com/cukes/requirements/tags.html)

**4. View all features and scenarios by tag** [example](http://recursivegames.com/cukes/requirements/tags/message.html)

**5. View Step Definitions and Transforms** [example](http://recursivegames.com/cukes/requirements/step_transformers.html)

**6. All steps [matched](http://recursivegames.com/cukes/requirements/step_transformers.html#definition_5-stepdefinition) to step definitions**

**7. [Steps](http://recursivegames.com/cukes/requirements/step_transformers.html#transform_3-steptransform) that have transforms applied to them**

**8. [Undefined steps](http://recursivegames.com/cukes/requirements/step_transformers.html#undefined_steps) and even [Rubular](http://rubular.com/) links of your step definitions.**

**9. Feature directories with a README.md will be parsed into the description** [example](http://recursivegames.com/cukes/requirements/features.html)

Installation
------------

Cucumber-In-The-Yard (CITY) requires the following gems installed:

    Gherkin - http://cukes.info
    Cucumber - http://cukes.info
    YARD - http://yardoc.org

To install CITY use the following command:

    $ gem install yard-cucumber
    
(Add `sudo` if you're installing under a POSIX system as root)

Usage
-----

YARD supports for automatically including gems with the prefix `yard-` 
as a plugin. To enable automatic loading yard-cucumber. 

1. Edit `~/.yard/config` and insert the following line:

    load_plugins: true

2. Run `yardoc`, use the rake task, or run `yard server`, as would [normally](https://github.com/lsegal/yard).

Be sure to update any file patterns so that they do not exclude `feature` 
files. yard-cucumber will even process your step definitions and transforms.

    $ yardoc 'example/**/*.rb' 'example/**/*.feature'

An example with the rake task:

    require 'yard'

    YARD::Rake::YardocTask.new do |t|
      t.files   = ['features/**/*.feature', 'features/**/*.rb']
      t.options = ['--any', '--extra', '--opts'] # optional
    end

Details
--------

There are two things that I enjoy: a test framework written in my own Domain
Specific Language (DSL) that is easily understood by all those on a project
and the ability for all participants to easily read, search, and view the tests.

Cucumber is an amazing tool that allowed me to define exercisable requirements. 
My biggest obstacle was bringing these requirements to my team, the product
owner, and other stakeholders.

Initially I tried to expose more of the functionality by providing freshly
authored requirements through email, attachments to JIRA tickets, or linked in
wiki documents. None of these methods were very sustainable or successful. 
First, I was continually pushing out the documents to those interested. 
Second, the documents were displayed to the user in text without the syntax
highlighting that was exceedingly helpful for quickly understanding the requirements.

I also found it hard to share the test framework that I had put together with
another developer that joined the team. It was difficult to direct them around
the features, tags, step definitions, and transforms. It was when I started to convey to them the conventions that I had established that I wished I had a
tool that would allow me to provide documentation like one would find generated 
by a great tool like YARD.

So I set out to integrate Cucumber objects like features, backgrounds, 
scenarios, tags, steps, step definitions, and transforms into a YARD template.
From my quick survey of the landscape I can see that the my needs are
different than a lot of others that use Cucumber.  The entire project that
spawned this effort was solely to exercise the functionality of a different,
large project and so there is a huge dependence on having the requirements
documented.  This is in contrast to other projects that are using this on a
small scale to test the functionality of small software component.  Though,
ultimately, I realized that the functionality may provide a valuable tool for
many as I feel it helps more solidly bridge the reporting of the documentation
by putting a coat of paint on it.


LICENSE
-------

(The MIT License)

Copyright (c) 2011 FIX

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.