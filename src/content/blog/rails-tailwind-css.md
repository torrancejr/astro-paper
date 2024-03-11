---
author: Ryan Torrance
pubDatetime: 2024-03-10T16:57:52.737Z
title: How to Add Tailwind CSS to your Rails 7 Project
slug: rails-7-and-tailwind-css
featured: true
ogImage: ././assets/images/tailwind-code.jpg
tags:
  - rails 7
  - css
  - tailwind
description: How to add Tailwind CSS to Rails 7
---

1. Install Tailwind CSS
Install the tailwindcss-rails gem, and then run the install command to generate a tailwind.config.js file in the ./config directory.
<pre> <code class="language-javascript">./bin/bundle add tailwindcss-rails
./bin/rails tailwindcss:install</code></pre>
2. Configure your template paths
Add the paths to all of your template files in your tailwind.config.js file. Plugins can be added using npm install @@tailwindcss/[plugin-name] and added to other required plugin names.
<pre><code class="language-rb">
const defaultTheme = require('tailwindcss/defaultTheme')

module.exports = {
content: [
'./public/*.html',
'./app/helpers/**/*.rb',
'./app/javascript/**/*.js',
'./app/views/**/*.{erb,haml,html,slim}'
],
theme: {
extend: {
fontFamily: {
sans: ['Inter var', ...defaultTheme.fontFamily.sans],
},
},
},
plugins: [
require('@tailwindcss/forms'),
require('@tailwindcss/aspect-ratio'),
require('@tailwindcss/typography'),
require('@tailwindcss/container-queries'),
]
}
</code>

</pre>
3.Add the Tailwind directives to your CSS
Add the @tailwind directives for each of Tailwind's layers to your application.tailwind.css file located in the ./app/assets/stylesheets directory.
</code>
<pre>
<code class="language-rb">
@tailwind base;
@tailwind components;
@tailwind utilities;
</code>
</pre>
4.Start your build process
Run your build process with ./bin/dev in your Terminal.
<pre>
<code class="language-rb">
./bin/dev.
</code>
</pre>
4.Start using Tailwind in your project
Start using Tailwind's utility classes to style your content.
Add this class to an h1 tag to test.
<pre>
<code class="language-rb">
class="text-3xl font-bold underline"
</code>
</pre>

[wixenco.com](https://wixenco.com)
<br/>
My new venture plug
