## Elements
 The diagrams below illustrate the class structure and relationships of all Elements in Harmony. All Elements inherit from the `Element` base class.

For readability and ease of navigation, the diagrams are divided into several smaller, interconnected components rather than presenting all classes in a single diagram.

These diagrams are intended to provide an overview of the class hierarchy and the relationships between classes, rather than document their individual implementations or functionality.

For detailed information about each class, including its properties and methods, please refer to the [API documentation](https://cresym.github.io/Harmony-Doc/api/index.html).


### Network and Passive Elements

<!-- ***************************************************************** -->
<!-- SWITCH -->
<!-- TRANSMISSION LINE -->
<!-- ***************************************************************** -->

<details>
  <summary>Switch and Transmission Line</summary>
  
```mermaid
---
title: Switch and Transmission Line
config:
  theme: redux-color
  themeVariables:
    fontFamily: Segoe UI, -apple-system, BlinkMacSystemFont, sans-serif
    lineColor: "#64748B"
    primaryTextColor: "#0F172A"
  flowchart:
    wrappingWidth: 450
  class:
    hideEmptyMembersBox: true
    padding: 16
---
classDiagram
  namespace Harmony-Elements {
    class Element {}
  }
  namespace Harmony-Elements.Switch {
    class Switch {}
  }
  Element <|-- Switch

  namespace Harmony-Elements.Transmission_Line {
    class Cable {}
    class Overhead_Line {}
    class Transmission_Line {}
  }
  Element <|-- Cable
  Element <|-- Overhead_Line
  Element <|-- Transmission_Line

```

</details>

<!-- ***************************************************************** -->
<!-- IMPEDANCE -->
<!-- ***************************************************************** -->

<details>
  <summary>Impedance</summary>
  
```mermaid
---
title: Impedance
config:
  theme: redux-color
  themeVariables:
    fontFamily: Segoe UI, -apple-system, BlinkMacSystemFont, sans-serif
    lineColor: "#64748B"
    primaryTextColor: "#0F172A"
  flowchart:
    wrappingWidth: 450
  class:
    hideEmptyMembersBox: true
    padding: 16
---
classDiagram
  namespace Harmony-Elements {
    class Element {}
  }
  namespace Harmony-Elements {
    class Impedance_base {}
    class Admittance {}
    class Impedance {}
    class Capacitor {}
    class Inductor {}
    class Resistor {}
  }
  Element <|-- Impedance_base
  Element <|-- Capacitor
  Element <|-- Inductor
  Element <|-- Resistor
  Impedance_base <|-- Admittance
  Impedance_base <|-- Impedance
```

</details>

<!-- ***************************************************************** -->
<!-- TRANSFORMERS -->
<!-- ***************************************************************** -->

<details>
  <summary>Transformers</summary>
  
```mermaid
---
title: Transformers
config:
  theme: redux-color
  themeVariables:
    fontFamily: Segoe UI, -apple-system, BlinkMacSystemFont, sans-serif
    lineColor: "#64748B"
    primaryTextColor: "#0F172A"
  flowchart:
    wrappingWidth: 450
  class:
    hideEmptyMembersBox: true
    padding: 16
---
classDiagram
  direction LR

  namespace Harmony-Elements {
    class Element {}
  }

namespace Harmony-Elements {
    class Transformer_base
    class Transformer_classic
    class Transformer_real
    class Transformer_Delta_Delta["Transformer_Delta_Delta"]
    class Transformer_Delta_Delta_real["Transformer_Delta_Delta<br/>_real"]
    class Transformer_Delta_Y["Transformer_Delta_Y"]
    class Transformer_Delta_Y_real["Transformer_Delta_Y<br/>_real"]
    class Transformer_Y_Delta["Transformer_Y_Delta"]
    class Transformer_Y_Delta_real["Transformer_Y_Delta<br/>_real"]
    class Transformer_Y_Y["Transformer_Y_Y"]
    class Transformer_Y_Y_real["Transformer_Y_Y_real"]
  }
  Element <|-- Transformer_base
  Transformer_base <|-- Transformer_classic
  Transformer_base <|-- Transformer_real
  Transformer_classic <|-- Transformer_Delta_Delta
  Transformer_classic <|-- Transformer_Delta_Y
  Transformer_classic <|-- Transformer_Y_Delta
  Transformer_classic <|-- Transformer_Y_Y
  Transformer_real <|-- Transformer_Delta_Delta_real
  Transformer_real <|-- Transformer_Delta_Y_real
  Transformer_real <|-- Transformer_Y_Delta_real
  Transformer_real <|-- Transformer_Y_Y_real
```

</details>


## Generators, Loads and Converters

<!-- ***************************************************************** -->
<!-- CONVERTER -->
<!-- ***************************************************************** -->

<details>
  <summary>Converter</summary>
  
```mermaid
---
title: Converter
config:
  theme: redux-color
  themeVariables:
    fontFamily: Segoe UI, -apple-system, BlinkMacSystemFont, sans-serif
    lineColor: "#64748B"
    primaryTextColor: "#0F172A"
  flowchart:
    wrappingWidth: 450
  class:
    hideEmptyMembersBox: true
    padding: 16
---
classDiagram
  namespace Harmony-Elements {
    class Element {}
  }
  namespace Harmony-Elements {
    class Converter {}
    class MMC {}
  }
  Element <|-- Converter
  Converter <|-- MMC 
```

</details>

<!-- ***************************************************************** -->
<!-- LOAD -->
<!-- ***************************************************************** -->

<details>
  <summary>Load</summary>
  
```mermaid
---
title: Load
config:
  theme: redux-color
  themeVariables:
    fontFamily: Segoe UI, -apple-system, BlinkMacSystemFont, sans-serif
    lineColor: "#64748B"
    primaryTextColor: "#0F172A"
  flowchart:
    wrappingWidth: 450
  class:
    hideEmptyMembersBox: true
    padding: 16
---
classDiagram
  direction LR
  namespace Harmony-Elements {
    class Element {}
  }
  namespace Harmony-Elements {
    class Load_base {}
    class LoadPQ {}
    class Load {}
  }
  Element <|-- Load_base
  Load_base <|-- LoadPQ
  Load_base <|-- Load
```

</details>

<!-- ***************************************************************** -->
<!-- RES -->
<!-- ***************************************************************** -->

<details>
  <summary>RES</summary>
  
```mermaid
---
title: RES
config:
  theme: redux-color
  themeVariables:
    fontFamily: Segoe UI, -apple-system, BlinkMacSystemFont, sans-serif
    lineColor: "#64748B"
    primaryTextColor: "#0F172A"
  flowchart:
    wrappingWidth: 450
  class:
    hideEmptyMembersBox: true
    padding: 16
---
classDiagram
  namespace Harmony-Elements {
    class Element {}
  }
  namespace Harmony-Elements {
    class PV_plant {}
    class RES_base {}
    class WP_plant {}
    class WT_type_3 {}
    class WT_type_4 {}
  }
  Element <|-- RES_base
  RES_base <|-- PV_plant
  RES_base <|-- WP_plant
  RES_base <|-- WT_type_3
  RES_base <|-- WT_type_4
```

</details>

<!-- ***************************************************************** -->
<!-- SOURCE -->
<!-- ***************************************************************** -->

<details>
  <summary>Source</summary>
  
```mermaid
---
title: Source
config:
  theme: redux-color
  themeVariables:
    fontFamily: Segoe UI, -apple-system, BlinkMacSystemFont, sans-serif
    lineColor: "#64748B"
    primaryTextColor: "#0F172A"
  flowchart:
    wrappingWidth: 450
  class:
    hideEmptyMembersBox: true
    padding: 16
---
classDiagram
  namespace Harmony-Elements {
    class Element {}
  }
  namespace Harmony-Elements {
    class Source_base {}
    class AC_source {}
    class DC_source {}
    class Generator {}
  }
  Element <|-- Source_base
  Source_base <|-- AC_source
  Source_base <|-- DC_source
  Source_base <|-- Generator
```

</details>

