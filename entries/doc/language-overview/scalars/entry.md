---
title: 2.3. Scalars
template: item
---

Scalar content can be written in block notation, using a literal style (indicated by “|”) where all line breaks are significant. Alternatively, they can be written with the folded style (denoted by “>”) where each line break is folded to a space unless it ends an empty or a more-indented line.

#### Example 2.13 In literals, newlines are preserved

```yaml
# ASCII Art
&dash;&dash;&dash; |
  \//||\/||
  // ||  ||__
```

#### Example 2.14 In the folded scalars, newlines become spaces

```yaml
&dash;&dash;&dash; >
  Mark McGwire's
  year was crippled
  by a knee injury.
```

#### Example 2.15 Folded newlines are preserved for “more indented” and blank lines

```yaml
&dash;&dash;&dash; >
 Sammy Sosa completed another
 fine season with great stats.

   63 Home Runs
   0.288 Batting Average

 What a year!
```

#### Example 2.16 Indentation determines scope

```yaml
name: Mark McGwire
accomplishment: >
  Mark set a major league
  home run record in 1998.
stats: |
  65 Home Runs
  0.278 Batting Average
YAML’s flow scalars include the plain style (most examples thus far) and two quoted styles. The double-quoted style provides escape sequences. The single-quoted style is useful when escaping is not needed. All flow scalars can span multiple lines; line breaks are always folded.
```

#### Example 2.17 Quoted Scalars

```yaml
unicode: "Sosa did fine.\u263A"
control: "\b1998\t1999\t2000\n"
hex esc: "\x0d\x0a is \r\n"

single: '"Howdy!" he cried.'
quoted: ' # Not a ''comment''.'
tie-fighter: '|\-*-/|'
```

#### Example 2.18 Multi-line Flow Scalars

```yaml
plain:
  This unquoted scalar
  spans many lines.

quoted: "So does this
  quoted scalar.\n"
```