---
layout: page
title: Font effects
parent: rcss
next: property_index
---

Font effects are an extension to CSS for RCSS for applying effects, such as outlining or shadowing, to text. Similarly to [decorators](decorators.html), font effects are declared and named in a style sheet like a property, and configured with font-effect-specific properties. Custom font effects can be developed to apply arbitrary effects onto text.

### RmlUi font effects

RmlUi comes with the following built-in font effects:

| Font effect                          | Types             | Description                    |
|--------------------------------------|-------------------|--------------------------------|
| [Glow](font_effects/glow.html)       | `glow`{:.prop}    | Glowing text and drop shadows. |
| [Outline](font_effects/outline.html) | `outline`{:.prop} | Outlining text.                |
| [Shadow](font_effects/shadow.html)   | `shadow`{:.prop}  | Rendering shadows.             |
| [Blur](font_effects/blur.html)       | `blur`{:.prop}    | Blurring text.                 |


### Properties
{:#font-effect}

Font effects are declared and configured within style sheets similar to how decorators are declared.

`font-effect`{:.prop}

Value: | none \| \[\<type\>( \<properties\> )\]<span class="prop-def-symbol" title="One or more comma-separated occurrences">#+</span>
Initial: | none
Inherited: | yes
Percentages: | N/A

`<type>`{:.prop} is a font effect type, and `<properties>`{:.prop} specify the properties of the given decorator type.

Multiple font effects can also be specified, eg.
```css
font-effect: <type>( <properties> ), <type>( <properties> ), ... ;
```
Multiple font effects are applied in reverse order.

Note that there is no RCSS at-rule for font effects as there is for decorators. Thus, the `font-effect`{:.prop} property cannot take a name.

#### Inheritance

Unlike decorators, font effects are inherited from parent elements. For example, the following declaration:

```css
h1
{
	font-effect: outline(2px black);
}
```

will add an outline to the text within all `h1`{:.tag} elements and their descendants. To prevent inheritance, override the effect with `none`{:.value}. For example, to prevent the `h1`{:.tag} outline effect from affecting `span`{:.tag} elements, you could specify the following:

```css
h1 span
{
	font-effect: none;
}
```
