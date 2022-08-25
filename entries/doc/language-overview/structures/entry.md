---
title: 2.2. Structures
template: item
---

YAML uses three dashes (“&dash;&dash;&dash;”) to separate directives from document content. This also serves to signal the start of a document if no directives are present. Three dots ( “...”) indicate the end of a document without starting a new one, for use in communication channels.

#### Example 2.7 Two Documents in a Stream (each with a leading comment)

```yaml
# Ranking of 1998 home runs
&dash;&dash;&dash;
- Mark McGwire
- Sammy Sosa
- Ken Griffey

# Team ranking
&dash;&dash;&dash;
- Chicago Cubs
- St Louis Cardinals
```

#### Example 2.8 Play by Play Feed from a Game

```yaml
&dash;&dash;&dash;
time: 20:03:20
player: Sammy Sosa
action: strike (miss)
...
&dash;&dash;&dash;
time: 20:03:47
player: Sammy Sosa
action: grand slam
...
```

Repeated nodes (objects) are first identified by an anchor (marked with the ampersand - “&”) and are then aliased (referenced with an asterisk - “*”) thereafter.

#### Example 2.9 Single Document with Two Comments

```yaml
&dash;&dash;&dash;
hr: # 1998 hr ranking
- Mark McGwire
- Sammy Sosa
# 1998 rbi ranking
rbi:
- Sammy Sosa
- Ken Griffey
Example 2.10 Node for “Sammy Sosa” appears twice in this document

&dash;&dash;&dash;
hr:
- Mark McGwire
# Following node labeled SS
- &SS Sammy Sosa
rbi:
- *SS # Subsequent occurrence
- Ken Griffey
A question mark and space (“? ”) indicate a complex mapping key. Within a block collection, key/value pairs can start immediately following the dash, colon or question mark.
```

#### Example 2.11 Mapping between Sequences

```yaml
? - Detroit Tigers
  - Chicago cubs
: - 2001-07-23

? [ New York Yankees,
    Atlanta Braves ]
: [ 2001-07-02, 2001-08-12,
    2001-08-14 ]
```

#### Example 2.12 Compact Nested Mapping

```yaml
&dash;&dash;&dash;
# Products purchased
- item    : Super Hoop
  quantity: 1
- item    : Basketball
  quantity: 4
- item    : Big Shoes
  quantity: 1
```