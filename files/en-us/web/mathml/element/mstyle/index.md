---
title: <mstyle>
slug: Web/MathML/Element/mstyle
tags:
  - MathML
  - MathML Reference
  - MathML:Element
  - MathML:General Layout Schemata
browser-compat: mathml.elements.mstyle
---
{{MathMLRef}}

The MathML `<mstyle>` element is used change the style of its children. It accepts all attributes of all MathML presentation elements with some exceptions and additional attributes listed below.

## Attributes

This element's attributes include the [global MathML attributes](/en-US/docs/Web/MathML/Global_attributes).

- `infixlinebreakstyle`
  - : Specifies the default `linebreakstyle` to use for infix operators. The values `before`, `after` and `duplicate` are allowed.
- `scriptminsize`
  - : Specifies a minimum font size allowed due to changes in `scriptlevel`. The default value is 8pt.
- `scriptsizemultiplier`
  - : Specifies the multiplier to be used to adjust font size due to changes in `scriptlevel`. The default value is 0.71.

The `<mstyle>` element accepts [all attributes](/en-US/docs/Web/MathML/Attribute) of all presentation elements with the following exceptions:

- `height`, `depth` or `width` do not apply to {{ MathMLElement("mpadded") }} or {{ MathMLElement("mtable") }}.
- `rowalign`, `columnalign`, or `groupalign` do not apply to {{ MathMLElement("mtr") }}, {{ MathMLElement("mtd") }} or {{ MathMLElement("maligngroup") }}.
- `lspace` or `voffset` do not apply to {{ MathMLElement("mpadded") }}.
- `align` does not apply to {{ MathMLElement("mtable") }} or {{ MathMLElement("mstack") }}.
- `index` cannot be set on `<mstyle>`.
- `actiontype` on {{ MathMLElement("maction") }} cannot be set on `<mstyle>`.

## Examples

Using `displaystyle` and `mathcolor` to effect style changes in the layout of the whole sum.

```html
<math>

  <mstyle displaystyle="true" mathcolor="teal">
    <mrow>

      <munderover>
        <mo stretchy="true" form="prefix">&sum;</mo>
        <mrow>
          <mi>i</mi>
          <mo form="infix">=</mo>
          <mn>1</mn>
        </mrow>
        <mi>n</mi>
      </munderover>

      <mstyle displaystyle="true">
        <mfrac>
          <mn>1</mn>
          <mi>n</mi>
        </mfrac>
      </mstyle>

    </mrow>
  </mstyle>

</math>
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## Gecko-specific notes

- Prior to Gecko 6.0 {{ geckoRelease("6.0") }} the implementation of `<mstyle>` was not complete and [has been corrected](https://bugzilla.mozilla.org/show_bug.cgi?id=569125). In particular, setting these attributes on `mstyle` had no effect to its children:

  - The `bevelled` attribute on {{ MathMLElement("mfrac") }} elements.
  - The `notation` attribute on {{ MathMLElement("menclose") }} elements.
  - The `open`, `close` and `separators` attributes on {{ MathMLElement("mfenced") }} elements.
  - The `accent` and `accentunder` attributes on {{ MathMLElement("mover") }}, {{ MathMLElement("munder") }} and {{ MathMLElement("munderover") }} elements.
  - The `selection` attribute on {{ MathMLElement("maction") }} elements.
  - The `mathvariant` attribute on {{ MathMLElement("mi") }} elements.

- Starting with Gecko 29.0 {{geckoRelease("29.0")}}, the attributes accepted on the `<mstyle>` element have been restricted to those actually used in practice: `id, class, style, href, mathcolor, mathbackground, scriptlevel, displaystyle, scriptsizemultiplier, scriptminsize, dir, mathsize, mathvariant, fontfamily, fontweight, fontstyle, fontsize, color, background`.
