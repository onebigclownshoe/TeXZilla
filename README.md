License
=======

This Source Code Form is subject to the terms of the Mozilla Public
License, v. 2.0. If a copy of the MPL was not distributed with this
file, You can obtain one at http://mozilla.org/MPL/2.0/.

Content
=======

This release contains the following files:

- README.md: this file.
- TeXZilla.js: TeXZilla parser generated by Jison.
- TeXZilla-min.js: TeXZilla.js minified with Google Closure.

TeXZilla
========

This is TeXZilla 0.9, a Javascript TeX-to-MathML converter which is compatible
with Unicode. This is still a work in progress and things may change in the
future. See https://github.com/fred-wang/TeXZilla/issues for known issues.
You can use TeXZilla in a commonJS program:

  var parser = require("./TeXZilla").parser;
  console.log(parser.toMathMLString("\\sqrt{\\frac{x}{2}+y}"));

or from a Web page:

  <script type="text/javascript" src="TeXZilla-min.js"></script>
  ...
  var MathMLElement = TeXZilla.toMathML("\\sqrt{\\frac{x}{2}+y}");

See also http://fred-wang.github.io/TeXZilla/ for a live demo.

The public API is:

  getTeXSource = function(aMathMLElement)

  returns the TeX source attached to aMathMLElement via a semantics annotation
  or null if none is found. aMathMLElement is either a string or a MathML DOM
  element.
  
  toMathMLString = function(aTeX, aDisplay, aRTL)

  converts the TeX string aTeX into a MathML source. The optional boolean
  aDisplay and aRTL indicates whether the MathML output should be in display
  mode and in RTL direction respectively.

  toMathML = function(aTeX, aDisplay, aRTL)

  Same as toMathMLString, but returns a MathML DOM element.
