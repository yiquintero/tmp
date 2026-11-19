```mermaid
---
title: Harmony
config:
  theme: redux-color
  themeVariables:
    fontFamily: Inter, Segoe UI, sans-serif
    lineColor: "#64748B"
    primaryTextColor: "#0F172A"
  class:
    hideEmptyMembersBox: true
---
classDiagram
  direction LR

  namespace Elements.Converter {
    class Converter {}
    class MMC {}
  }
  %%Element --> Converter
  Converter --> MMC 

  namespace Elements.Impedance {
    class Impedance_base {}
    class Admittance {}
    class Impedance {}
    class Capacitor {}
    class Inductor {}
    class Resistor {}
  }
  %%Element --> Impedance_base
  %%Element --> Capacitor
  %%Element --> Inductor
  %%Element --> Resistor
  Impedance_base --> Admittance
  Impedance_base --> Impedance

  namespace Elements.Load {
    class Load_base {}
    class LoadPQ {}
    class Load {}
  }
  %%Element --> Load_base
  Load_base --> LoadPQ
  Load_base --> Load

  namespace Elements.RES {
    class PV_plant {}
    class RES_base {}
    class WP_plant {}
    class WT_type_3 {}
    class WT_type_4 {}
  }
  %%Element --> RES_base
  RES_base --> PV_plant
  RES_base --> WP_plant
  RES_base --> WT_type_3
  RES_base --> WT_type_4

  namespace Elements.Source {
    class Source_base {}
    class AC_source {}
    class DC_source {}
    class Generator {}
  }
  %%Element --> Source_base
  Source_base --> AC_source
  Source_base --> DC_source
  Source_base --> Generator

  namespace Elements.Switch {
    class Switch {}
  }
  %%Element --> Switch

  namespace Elements.Transformer {
    class Transformer_base {}
    class Transformer_classic {}
    class Transformer_Delta_Delta_real {}
    class Transformer_Delta_Delta {}
    class Transformer_Delta_Y_real {}
    class Transformer_Delta_Y {}
    class Transformer_real {}
    class Transformer_Y_Delta_real {}
    class Transformer_Y_Delta {}
    class Transformer_Y_Y_real {}
    class Transformer_Y_Y {}
  }
  %% Element --> Transformer_base
  Transformer_base --> Transformer_classic
  Transformer_real --> Transformer_Delta_Delta_real
  Transformer_classic --> Transformer_Delta_Delta 
  Transformer_real --> Transformer_Delta_Y_real
  Transformer_classic --> Transformer_Delta_Y
  Transformer_base --> Transformer_real
  Transformer_real --> Transformer_Y_Delta_real
  Transformer_classic --> Transformer_Y_Delta
  Transformer_real --> Transformer_Y_Y_real
  Transformer_classic --> Transformer_Y_Y

  namespace Elements.Transmission_Line {
    class Cable {}
    class Overhead_Line {}
    class Transmission_Line {}
  }
  %% Element --> Cable
  %% Element --> Overhead_Line
  %% Element --> Transmission_Line
```
