# Contributing to this documentation

This documentation is generated using [Sphinx](https://www.sphinx-doc.org/en/master/index.html). The source for the text content is built in different markdown files, and the code for the website is generated based on that.

When you push to GitHub, a GitHub action will run to generate the website based on the Markdown, and a few minutes later the website will update. You don't need to worry about generating the website code from the Markdown, that is automated.

The one # heading at the top of each Markdown file creates the name of the page. Subheadings with two #s will also appear in the table of content.

## Edit an existing page

Just modify the cooresponding markdown file (in doc/src/your-file.md) and push to GitHub. 

## Add a new page

1. Add a new Markdown file under doc/src. Please use camel case for the name (exampleFileName.md). 
2. Add your Markdown content to the file. 
3. Open doc/index.rst and add the your file path relative to the index.rst file under the list of files already there. The path you add here should be src/whateverFileName.md and adding your file to this file adds it to the table of contents. For example, if your file is src/sonar.md you would add the line src/sonar.md under the existing files there. Changing the order of files here changes the order in the table of contents.
4. Push to GitHub.