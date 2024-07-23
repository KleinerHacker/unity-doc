# Overview

The Unity Extension System is a big toolbox of a lot of additional components and tooling to make it easier
to create your game. It contains:
* Basic extensions
  * Dispatcher
  * Behavior Helper
  * Cursor System
  * Singleton Support
* Advanced extensions
  * Extended Effect System
  * Hovering
* UI
  * Components
    * Lists
    * Image Switcher
    * Windows / Dialogs
  * Cursor System extension
  * Jingle System
  * Shortcut System
* Audio
  * Background SFX
  * Background Music
* Preferences System extension
* Animation extension (Coroutines)
* Scene System
  * Blending between Scenes
  * World System (multiple Scenes)
* Game Tooling
  * Camera Systems
  * Traffic Light System

## Architecture

In the following diagram you can see the dependency between the libs:

<code-block lang="d2">
    direction: up
    dependencies: Dependencies {
      base: Unity Base { 
        style.stroke: red
      }
      editor: Unity Editor { 
        style.stroke: red
      }
      commons: Unity Commons {
        style.stroke: gold
      }
      animation: Unity Animation {
        style.stroke: green
      }
      pref: Unity Preferences {
        style.stroke: green
      }
      loader: Unity Asset Loader {
        style.stroke: green
      }
      ui: Unity UI
      extension: Unity Extension
      commons -> base {
        style.stroke: gold
      }
      commons -> animation {
        style.stroke: gold
      }
      commons -> loader {
        style.stroke: gold
      }
      commons -> editor {
        style.stroke: gold
      }
      animation -> base {
        style.stroke: green
      }
      pref -> base {
        style.stroke: green
      }
      loader -> base {
        style.stroke: green
      }
      ui -> commons
      ui -> base
      ui -> animation
      ui -> loader
      ui -> editor
      extension -> base
      extension -> editor
      extension -> commons
    }
    legend: Legend {
      red: Basic Components (for all) {
        style.stroke: red
      }
      green: Atomic Components (independent) {
        style.stroke: green
      }
      yellow: Commons Components (only for end components){
        style.stroke: gold
      } 
      blue: End Components
    }
    legend -> dependencies {
      style.stroke: transparent
    }
</code-block>