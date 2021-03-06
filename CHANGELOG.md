# HEAD

 * Removing some unnecessary lint plugins and using native - Jon Rohan [github/github@2ae0070](https://github.com/github/github/commit/2ae0070)
 * including no-utility lint plugin - Jon Rohan [github/github@5cb86ed](https://github.com/github/github/commit/5cb86ed)
 * Disabling utility check - Jon Rohan [github/github@e92dbf4](https://github.com/github/github/commit/e92dbf4)
 * Adding lint plugins for new config - Jon Rohan [github/github@7fb9613](https://github.com/github/github/commit/7fb9613)

# v3.1.2

 * Mentioning the build file - Jon Rohan [github/github@64ca4a7](https://github.com/github/github/commit/64ca4a7)
 * Including build/build.css in distributed npm module - Jon Rohan [github/github@e4effbf](https://github.com/github/github/commit/e4effbf)
 * Updating modules to run on prepublish to include build.css in distribution - Jon Rohan [github/github@5b573a0](https://github.com/github/github/commit/5b573a0)
 * Re-ordering the docs to the bottom of the readme - Jon Rohan [github/github@9c1f291](https://github.com/github/github/commit/9c1f291)
 * Updating the link - Jon Rohan [github/github@f67684b](https://github.com/github/github/commit/f67684b)

# v3.1.1

 * Bumping version to include postcss.json in npm - Jon Rohan [github/github@9e560ba](https://github.com/github/github/commit/9e560ba)
 * Using stylelint to lint the modules instead of scss_lint - Jon Rohan [github/github@cb0b8fd](https://github.com/github/github/commit/cb0b8fd)
 * Updating for stylelint instead of scss_lint - Jon Rohan [github/github@87a2c68](https://github.com/github/github/commit/87a2c68)

# v3.1.0

 * Don't link requirements - Jon Rohan [github/github@7740e81](https://github.com/github/github/commit/7740e81)
 * Updating the README with more detailed instructions - Jon Rohan [github/github@5dd7c34](https://github.com/github/github/commit/5dd7c34)
 * Bumping the version - Jon Rohan [github/github@01e7c4e](https://github.com/github/github/commit/01e7c4e)
 * Reorganize the module folders into a more flexible organization - Jon Rohan [github/github@5a07101](https://github.com/github/github/commit/5a07101)
 * cleaning up the package.json files - Jon Rohan [github/github@77763a1](https://github.com/github/github/commit/77763a1)
 * Adding npm version badges to readme - Jon Rohan [github/github@90b1871](https://github.com/github/github/commit/90b1871)

# v3.0.0

 * Adding travis build status - Jon Rohan [github/github@5758f9e](https://github.com/github/github/commit/5758f9e)
 * Moving primer-markdown to a css module - Jon Rohan [github/github@96b9132](https://github.com/github/github/commit/96b9132)

# v2.5.1
Fixes #59Override background-color on `.emoji` so it doesn't look awkward in zebra striped tables.

# v2.5.0
Add Apple Emoji to default font stackImproves emoji color rendering in Chrome.

# v2.4.0
Make Windows color emoji work in Markdown contentSpecifying Segoe UI Emoji gives us color emoji on Windows 8.1 and newer.Windows 7 and 8 will render monochrome emoji without any extra work onour part, but specifying Segoe UI Symbol gives us slightly better renderingin IE for a few glyphs. This also matches Primer's non-Markdown font stack.

# v2.3.0
Adding clearfix to the markdown body.

# v2.2.3
Changing to content-box on images

# v2.2.2


# v2.2.1
Updates to left and right aligned images

# v2.2.0


# v2.1.9
Remove overflow: hidden on `.markdown-body`

# v2.1.8
Fixin' some links in README and CONTRIBUTINGUpdate README.mdRemove apostropheLooks like the repo changed its name at one point + a copy paste derpfrom twbs/bootstrap.Speaking of which, it might be worth tweaking the “Feature Requests”guidelines in light of GH not really wanting any for Primer :-)

# v2.1.7
Make links in comments underlined on hover in SafariSafari 8 has a bug with the a:not(:link):not(:visited) selector we wereusing previously (see https://bugs.webkit.org/show_bug.cgi?id=142737).Now we use a:not([href]) instead, which should cover all of the cases wecare about (namely, <a name="foo"> elements explicitly created usingHTML syntax in Markdown).

# v2.1.6
Remove link styles on non-link anchors in user contentIt seems to be fairly common for users to write Markdown like thefollowing:    <a name="examples" />    Examples    ========    Here are some examples:This will generate the following HTML:    <p><a name="examples" /></p>    <h2>Examples</h2>    <p>Here are some examples:</p>github.com's current sanitizer (Sanitize 2.0.4) respects self-closingtag syntax (because it is built on top of libxml2, an XML parser, andself-closing tags are an XML thing). So when this gets run throughSanitize 2.0.4, you end up with the following HTML:    <p><a name="examples"></a></p>    <h2>Examples</h2>    <p>Here are some examples:</p>However, both Sanitize 3.x and the new sanitizer we're developing forgithub.com are based on an HTML-compliant parser rather than libxml2.HTML parsers treat this markup differently, and produce the following:    <p><a name="examples"></a></p><a name="examples">    <h2>Examples</h2>    <p>Here are some examples:</p></a>Browsers do the exact same thing given this HTML, as you can see in theLive DOM Viewer[1].Forgetting to close a non-link anchor, or using self-closing tag syntax(which also leaves the tag unclosed) is not normally a problem. Browsersdon't apply any styles to these elements by default, so many web authorsnever even notice they've made this mistake. But github.com applies linkstyles to all anchor elements whether or not they're actually links, sothis mistake becomes very noticeable: suddenly large parts of yourdocument are blue!Changing all of github.com's CSS to only target a:link and a:visitedelements would be a huge change that is probably not worth the effort.Instead, we'll remove the link styles from non-link anchor elements inuser content.[1]: http://software.hixie.ch/utilities/js/live-dom-viewer/?%3C!DOCTYPE%20html%3E%0A%3Cp%3E%3Ca%20name%3D%22examples%22%20%2F%3E%3C%2Fp%3E%0A%3Ch2%3EExamples%3C%2Fh2%3E%0A%3Cp%3EHere%20are%20some%20examples%3A%3C%2Fp%3E%0A

# v2.1.5
Fix emoji being shrunk by max-width on `img`This overrides the max-width set on `.markdown-body img`so that emojiwould not be shrunk.

# v2.1.4


# v2.1.3
Anchor link alignmentAdd <kbd> stylingKilling the syntax theme and ace syntax theme out of user-contentIgnore render-test.mdre https://github.com/github/github/pull/35950We don't need to distribute this file.

# v2.0.0


# 2.1.2
Anchor link alignment

# 2.1.1
Add <kbd> styling

# 2.1.0
Killing the syntax theme and ace syntax theme out of user-content

# 2.0.1
Ignore render-test.mdre https://github.com/github/github/pull/35950New syntax themes, adding ace editor syntaxdon't set height on .anchorFix styling of closing brackets in Ruby interpolated stringsWe need to override the normal .h style in this case.This is for our style guide https://github.com/styleguide/cssSupport recursive grammars by resetting CSS scopesUnder our new TextMate-based highlighting, we can end up with nestedhighlighting <span>s. In some cases we need to reset the highlightingstyles to match the top-level styles. This makes it so that, e.g., codeinside interpolated strings is colored as code rather than as stringtext. The new <span class="h"> elements that the TextMate highlighterproduces indicate where this needs to happen, and the styles added inthis commit accomplish the reset.See https://github.com/github/lex-luthor/issues/31 andhttps://github.com/github/github/pull/34312 for more discussion.We don't need to distribute this file.

# 1.2.9
Fix code strikethroughs

# 1.2.8
Revert keyword type changeNew color made keywords indistinguishable fromfunctions in certain cases. This change causescss scale values (px, (r)em, etc.) to appeardifferently than the associated number value,but we may just have to make that compromise for now.Organize syntax styles
 * Groups and combines related selectorsMissed the base number literal classUpdate syntax highlightingTake syntax highlighted diffs into account and tweakcontrast for words affected by intra-line highlighting.Fix underpants typoUnless this is some sort of weird Michigan dialect @bkeepers.Add task lists to sample documentAdd Markdown render test file

# 1.2.7
Make sure code lines don't wrap

# 1.2.6
Add word-break: break-word

# 1.2.5
Segoe UI for Windows Markdown![](http://cl.ly/image/2N0g23333x2i/content#png)Thoughts? This is with `font-size: 15px` (for some reason, Segoe always looks better when the font size is an odd number), I'm not sure how to do that via pure CSS though, probably need a "If Windows" stylesheet. Just changing it to Segoe looks better too though:![](http://cl.ly/image/3l2w032b3y3d/content#png)

# 1.2.4
Make sure plain <pre> elements have bottom margin

# 1.2.3
Add bottom margin to all header sizes
 * master:  bump to 1.2.2  fix margins on code inside .highlight containers  use top margins for paragraphs in nested lists  use rgba for code background colorsConflicts:	bower.json	package.json

# 1.2.2


# 1.2.10
Support recursive grammars by resetting CSS scopesUnder our new TextMate-based highlighting, we can end up with nestedhighlighting <span>s. In some cases we need to reset the highlightingstyles to match the top-level styles. This makes it so that, e.g., codeinside interpolated strings is colored as code rather than as stringtext. The new <span class="h"> elements that the TextMate highlighterproduces indicate where this needs to happen, and the styles added inthis commit accomplish the reset.See https://github.com/github/lex-luthor/issues/31 andhttps://github.com/github/github/pull/34312 for more discussion.Fix code strikethroughsRevert keyword type changeNew color made keywords indistinguishable fromfunctions in certain cases. This change causescss scale values (px, (r)em, etc.) to appeardifferently than the associated number value,but we may just have to make that compromise for now.Organize syntax styles
 * Groups and combines related selectorsMissed the base number literal classUpdate syntax highlightingTake syntax highlighted diffs into account and tweakcontrast for words affected by intra-line highlighting.Fix underpants typoUnless this is some sort of weird Michigan dialect @bkeepers.Add task lists to sample documentAdd Markdown render test fileMake sure code lines don't wrapAdd word-break: break-wordSegoe UI for Windows MarkdownMake sure plain <pre> elements have bottom marginAdd bottom margin to all header sizes
 * master:  bump to 1.2.2  fix margins on code inside .highlight containers  use top margins for paragraphs in nested lists  use rgba for code background colorsConflicts:	bower.json	package.jsonMore Markdown tweaksThis is so code blocks on shaded tables cells are still visible.![](http://cl.ly/image/2N0g23333x2i/content#png)Thoughts? This is with `font-size: 15px` (for some reason, Segoe always looks better when the font size is an odd number), I'm not sure how to do that via pure CSS though, probably need a "If Windows" stylesheet. Just changing it to Segoe looks better too though:![](http://cl.ly/image/3l2w032b3y3d/content#png)

# 1.2.1
Make h1 and h2 headings bold like the othersRemove explicit code/tt colorThis was overriding the blue link colors so commit referencesdidn't look clickable.

# 1.2.0
[WIP] Smaller headings in .markdown-bodybased on @mdo's recommendationsUnstripe <hr> elements

# 1.1.0


# 1.0.0
Finish rename to user-contentOverhaul to restructure, add tooling, add docs
 * Updated readme to include local dev instructions, license, SemVer guidelines, and more
 * Add package.json and bower.json
 * Add Gruntfile to compile .scss into .css (includes minified variation) via grunt-sass
 * Drop hr.png file for a base64 encoded image for fewer assets
 * Add MIT license file
 * Add .gitignore file