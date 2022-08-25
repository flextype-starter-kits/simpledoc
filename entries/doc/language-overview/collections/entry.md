---
title: 2.1. Collections
template: item
---

YAML’s block collections use indentation for scope and begin each entry on its own line. Block sequences indicate each entry with a dash and space (“- ”). Mappings use a colon and space (“: ”) to mark each key/value pair. Comments begin with an octothorpe (also called a “hash”, “sharp”, “pound” or “number sign” - “#”).

#### Example 2.1 Sequence of Scalars (ball players)

```yaml
- Mark McGwire
- Sammy Sosa
- Ken Griffey
```

#### Example 2.2 Mapping Scalars to Scalars (player statistics)

```yaml
hr:  65    # Home runs
avg: 0.278 # Batting average
rbi: 147   # Runs Batted In
```

#### Example 2.3 Mapping Scalars to Sequences (ball clubs in each league)

```yaml
american:
- Boston Red Sox
- Detroit Tigers
- New York Yankees
national:
- New York Mets
- Chicago Cubs
- Atlanta Braves
```

#### Example 2.4 Sequence of Mappings (players’ statistics)

```yaml
-
  name: Mark McGwire
  hr:   65
  avg:  0.278
-
  name: Sammy Sosa
  hr:   63
  avg:  0.288
```

YAML also has flow styles, using explicit indicators rather than indentation to denote scope. The flow sequence is written as a comma separated list within square brackets. In a similar manner, the flow mapping uses curly braces.