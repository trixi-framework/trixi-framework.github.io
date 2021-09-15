<!--
Add here global page variables to use throughout your website.
-->
+++
author = "<a href=\"https://github.com/trixi-framework/Trixi.jl/blob/main/AUTHORS.md\" target=\"_blank\" rel=\"noopener noreferrer\">The Trixi Authors</a>"
mintoclevel = 2

# Add here files or directories that should be ignored by Franklin, otherwise
# these files might be copied and, if markdown, processed by Franklin which
# you might not want. Indicate directories by ending the name with a `/`.
# Base files such as LICENSE.md and README.md are ignored by default.
ignore = ["node_modules/"]

# RSS (the website_{title, descr, url} must be defined to get RSS)
generate_rss = true
website_title = "Trixi Framework"
website_descr = "Overview of the activities within the Trixi Framework"
website_url   = "https://trixi-framework.github.io/landing-page/"
+++

@def prepath = "landing-page"

<!--
Add here global latex commands to use throughout your pages.
-->
\newcommand{\R}{\mathbb R}
\newcommand{\scal}[1]{\langle #1 \rangle}
