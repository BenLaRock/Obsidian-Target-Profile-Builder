# Privacy and Attribution
- People pictures were created with https://this-person-does-not-exist.com/en
- People names were created with https://randomwordgenerator.com/name.php
- Fake emails were created with https://generator.email/
- Fake phones were created with https://randommer.io/Phone

Makes use of Google Earth
- https://medium.com/the-first-digit/osint-trick-overlaying-drone-footage-onto-google-earth-181b611054b5

Google Attribution:
- https://about.google/brand-resource-center/products-and-services/geo-guidelines/#required-attribution
- https://about.google/brand-resource-center/guidance/

Google Earth:
- https://about.google/brand-resource-center/products-and-services/geo-guidelines/
#### Web and apps

Google Earth may not be embedded online or in apps. However, you’re welcome to export and use a handful of static images, with [proper attribution](https://about.google/brand-resource-center/products-and-services/geo-guidelines/#required-attribution), for non-commercial purposes such as news, blogs, educational, recreational, or instructional use.

If you’re using Google Earth content in an online video (e.g. YouTube) primarily for educational, instructional, recreational, or entertainment purposes, you don’t need to request permission, even if your work is monetized. But you must still follow our [general guidelines](https://about.google/brand-resource-center/products-and-services/geo-guidelines/#general-guidelines) and [attribute properly](https://about.google/brand-resource-center/products-and-services/geo-guidelines/#required-attribution).

# Python
- Look at Marko package for parsing markdown?
- Try Python-Markdown library
	- `pip install markdown`
- Use python-pptx package to create PPTs (can use an existing file as a template)
	- `pip install python-pptx`
- Maybe look at Node XL package to recreate links and embed a link chart / create standalone graph
- https://www.honeybadger.io/blog/python-markdown/

# Markdown parsing
- Because Obsidian just uses pure markdown, content isn't stored in a DOM / XML like structure and is then not easy to parse easily (keeping content separate)
- Built in Obsidian tags almost work except that:
	- 1 they clutter up the graph view (and add a lot of redundant tags)
	- They are parsed as H1 tags in HTML which is not accurate to how Obsidian uses them
- Raw HTML doesn't always work well with internal links
	- Couldn't get pictures to render with img tags
	- Internal links wouldn't work with a hrefs
	- Also raw HTML doesn't look great and could be confusing when editing
	- And it's a little unwieldly to create new list item tags 
	- Obsidian doesn't natively support CSS tags
- Tried the Markdown Attributes plugin (v1.2.2) which worked fairly well and allowed me to add CSS-like suffixes to content (something {.fakeAttribute}) which become invisible when not editing
	- However I couldn't always get this to work; for example, I couldn't get it to work following p tags
- I also played using empty span tags with CSS classes *before* or *after* content (cannot wrap content or links and image embedding stops working correctly) but this is a lot of extra typing
- Ultimately, looks like "Code" prefix tags like: `Identifier` work best:
	- Easy to type 
	- Doesn't interfere with tagging / linking (even on same line)
	- No glitchiness
	- Look clean
	- Doesn't interfere with other separate uses of the code markdown to include actual Python code, etc.
