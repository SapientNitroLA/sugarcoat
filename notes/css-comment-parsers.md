# CSS

- **Topdoc** <https://github.com/topcoat/topdoc/>
  - Requires "topdoc" tag in the beginning of a css comment: `/* topdoc */`
  
**Example**

```
/* topdoc
  name: Button
  description: A simple button
  modifiers:
    :active: Active state
    .is-active: Simulates an active state on mobile devices
    :disabled: Disabled state
    .is-disabled: Simulates a disabled state on mobile devices
  markup:
    <a class="topcoat-button">Button</a>
    <a class="topcoat-button is-active">Button</a>
    <a class="topcoat-button is-disabled">Button</a>
  example: http://codepen.io/
  tags:
    - desktop
    - light
    - mobile
    - button
    - quiet
  blarg: very true
*/
```

**Outputs**

```
{
  "title": "Button",
  "filename": "button.css",
  "source": "test/cases/button.css",
  "template": "lib/template.jade",
  "url": "index.html",
  "components": [
    {
      "name": "Button",
      "slug": "button",
      "details": ":active - Active state\n.is-active - Simulates an active state on mobile devices\n:disabled - Disabled state\n.is-disabled - Simulates a disabled state on mobile devices",
      "markup": "<a class=\"topcoat-button\">Button</a>\n<a class=\"topcoat-button is-active\">Button</a>\n<a class=\"topcoat-button is-disabled\">Button</a>",
      "css": ".topcoat-button,\n.topcoat-button--quiet,\n.topcoat-button--large,\n.topcoat-button--large--quiet,\n.topcoat-button--cta,\n.topcoat-button--large--cta {\n  position: relative;\n  display: inline-block;\n  vertical-align: top;\n  -webkit-box-sizing: border-box;\n  -moz-box-sizing: border-box;\n  box-sizing: border-box;\n  -webkit-background-clip: padding;\n  -moz-background-clip: padding;\n  background-clip: padding-box;\n  padding: 0;\n  margin: 0;\n  font: inherit;\n  color: inherit;\n  background: transparent;\n  border: none;\n  cursor: default;\n  -webkit-user-select: none;\n  -moz-user-select: none;\n  -ms-user-select: none;\n  user-select: none;\n  -o-text-overflow: ellipsis;\n  text-overflow: ellipsis;\n  white-space: nowrap;\n  overflow: hidden;\n  padding: 0 1.16rem;\n  font-size: 12px;\n  line-height: 2rem;\n  letter-spacing: 1px;\n  color: #c6c8c8;\n  text-shadow: 0 -1px rgba(0,0,0,0.69);\n  vertical-align: top;\n  background-color: #595b5b;\n  -webkit-box-shadow: inset 0 1px rgba(255,255,255,0.12);\n  box-shadow: inset 0 1px rgba(255,255,255,0.12);\n  border: 1px solid rgba(0,0,0,0.36);\n  -webkit-border-radius: 3px;\n  border-radius: 3px;\n}\n.topcoat-button:active,\n.topcoat-button.is-active,\n.topcoat-button--large:active,\n.topcoat-button--large.is-active {\n  background-color: #404141;\n  -webkit-box-shadow: inset 0 1px rgba(0,0,0,0.18);\n  box-shadow: inset 0 1px rgba(0,0,0,0.18);\n}\n.topcoat-button:disabled,\n.topcoat-button.is-disabled {\n  opacity: 0.3;\n  cursor: default;\n  pointer-events: none;\n}\n"
    },
    {
      "name": "Quiet Button",
      "slug": "quiet-button",
      "details": ":active - Quiet button active state\n.is-active - Simulates active state for a quiet button on touch interfaces\n:disabled - Disabled state\n.is-disabled - Simulates disabled state",
      "markup": "<a class=\"topcoat-button--quiet\">Button</a>\n<a class=\"topcoat-button--quiet is-active\">Button</a>\n<a class=\"topcoat-button--quiet is-disabled\">Button</a>",
      "css": ".topcoat-button--quiet {\n  background: transparent;\n  border: 1px solid transparent;\n  -webkit-box-shadow: none;\n  box-shadow: none;\n}\n.topcoat-button--quiet:active,\n.topcoat-button--quiet.is-active,\n.topcoat-button--large--quiet:active,\n.topcoat-button--large--quiet.is-active {\n  color: #c6c8c8;\n  text-shadow: 0 -1px rgba(0,0,0,0.69);\n  background-color: #404141;\n  border: 1px solid rgba(0,0,0,0.36);\n  -webkit-box-shadow: inset 0 1px rgba(0,0,0,0.18);\n  box-shadow: inset 0 1px rgba(0,0,0,0.18);\n}\n.topcoat-button--quiet:disabled,\n.topcoat-button--quiet.is-disabled {\n  opacity: 0.3;\n  cursor: default;\n  pointer-events: none;\n}\n"
    }
  ]
}
```

---

- css-parse <https://github.com/reworkcss/css-parse> / <https://github.com/reworkcss/css>
  - A rule-level or declaration-level comment. Comments inside selectors, properties and values etc. are lost.

---

- **yuidoc** <http://yui.github.io/yuidoc/>
	- Accepts /* */ in any type of file (CSS in this case)
  - requires documentation in specific form

---

- **Markdown Styleguide Generator** <https://github.com/emiloberg/markdown-styleguide-generator>
  - pure example, renders a template from md
  - requires prefixed `/* SOME_VAR */`
  - multiple file extensions
  - outputs javascript object
  - accepts *handlebars* template
 
**Example**

```
	/* SG
	# Glyphs/Style
	
	You may resize and change the colors of the icons with the `glyph-`-classes. Available sizes and colors listed:
	
	```html_example
	<p>
	    <i class="icon-search glyph-1x"></i>
	    <i class="icon-search glyph-1_5x"></i>
	    <i class="icon-search glyph-2x"></i>
	    <i class="icon-search glyph-3x"></i>
	</p>
	<p>
	    <i class="icon-search glyph-red"></i>
	</p>
	```
	*/
```

**Output**

```
{
    sections: [
        {
            id: 'HTML safe unique identifier',
            section: 'Section Name (from the "# Section/Heading" Markdown)',
            heading: 'Heading Name (from the "# Section/Heading" Markdown)',
            code: 'HTML Code',
            markup: 'Highlighted HTML Code',
            comment: 'Markdown comment converted to HTML',
        },
        {...}
    ],
    menu: [
        {
            name: 'Section Name (one per unique "# Section")',
            headings: [
                {
                    id: 'HTML safe unique identifier',
                    name: 'Heading Name'
                },
                {...}
            ]
        },
        {...}
    ]
}
```