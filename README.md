QFlashcard (quasar-app-extension-qflashcard)
===

![official icon](https://img.shields.io/badge/Quasar%201.0-Official%20UI%20App%20Extension-blue.svg)
![npm (scoped)](https://img.shields.io/npm/v/@quasar/quasar-app-extension-qflashcard.svg?style=plastic)
[![GitHub code size in bytes](https://img.shields.io/github/languages/code-size/quasarframework/app-extension-qflashcard.svg)]()
[![GitHub repo size in bytes](https://img.shields.io/github/repo-size/quasarframework/app-extension-qflashcard.svg)]()
[![npm](https://img.shields.io/npm/dt/@quasar/quasar-app-extension-qflashcard.svg)](https://www.npmjs.com/package/@quasar/quasar-app-extension-qflashcard)

QFlashcard is an `UI App Extension` for [Quasar Framework v1](https://v1.quasar-framework.org/). It will not work with legacy versions of Quasar Framework.

This work is currently in `beta` and there are expected changes while things get worked out. Your help with testing is greatly appreciated.

# Installation
To add this App Extension to your Quasar application, run the following (in your Quasar app folder):
```
quasar ext add @quasar/qflashcard
```

# Describe
You can use `quasar describe QFlashcard` or `quasar describe QFlashcardSection`

# Test Project
In **demo** folder of **app-extension-qflashcard**.

# Demo
Can be found [here](https://quasarframework.github.io/app-extension-qflashcard/).

# Example Code
This example mashes up the **nudge-in**, **fade-in**, and **slide-up-in** transitions.

```html
<q-flashcard :style="style">
  <q-flashcard-section transition="nudge-in">
    <img src="statics/2.jpg" width=300 height=200>
  </q-flashcard-section>
  <q-flashcard-section transition="fade-in" class="fit">
    <div class="fit" style="background-color: rgba(219,127,8, 0.7);" />
    <q-flashcard-section transition="drop-down" class="text-center my-header">
      Mashup Demo #1
    </q-flashcard-section>
    <q-flashcard-section transition="slide-up-in" class="my-text">
      For beautiful eyes, look for the good in others; for beautiful lips, speak only words of kindness; and for poise, walk with the knowledge that you are never alone.
    </q-flashcard-section>
    <q-flashcard-section transition="fade-in" class="fit flex justify-center items-end">
      <a href="#" class="my-button">Learn More</a>
    </q-flashcard-section>
  </q-flashcard-section>
</q-flashcard>

```
where **style** for the QFlashcard is defined as:
```js
computed: {
  style () {
    return {
      width: '320px',
      height: '220px',
      backgroundImage: 'url(../statics/bgimg.jpg)',
      padding: '10px',
      border: '10px solid #fff',
      textAlign: 'center',
      boxShadow: '1px 1px 2px #e6e6e6'
    }
  }
}
```

# QFlashcard
QFlashcard has no properties, events or methods. It has a single "default" slot. It expects one or more QFlashcardSection components to fill the slot.

# QFlashcardSection Vue Properties
| Vue&nbsp;Property | Type	| Description |
|---|---|---|
| transition | String,Array | [optional] The type of transition to use (listed below) |

QFlashcardSection has no events or methods. It has a single "default" slot. You can put anything into this slot.

# Transitions
The list of currently available transitions are as follows:

| Transition name |
|---|
| fade-in |
| fade-out |
| flip-left-in |
| flip-left-out |
| flip-right-in |
| flip-right-out |
| flip-down-in |
| flip-down-out |
| flip-up-in |
| flip-up-out |
| nudge-in |
| nudge-out |
| roll-in-left |
| roll-in-right |
| roll-in-down |
| roll-in-up |
| roll-out-left |
| roll-out-right |
| roll-out-down |
| roll-out-up |
| shake-left |
| shake-right |
| shake-down |
| shake-up |
| slide-in-left |
| slide-in-right |
| slide-in-down |
| slide-in-up |
| slide-out-left |
| slide-out-right |
| slide-out-down |
| slide-out-up |
| spin-in |
| spin-out |
| zoom-in |
| zoom-out |

# Combining Transitions
It is important to note that you have the ability to combine different transitions on the same `QFlashcardSection`. For instance, both of these examples are acceptable:
```html
<q-flashcard-section transition="nudge-out fade-out">

<q-flashcard-section transition="['nudge-out', 'fade-out']">
">
```
Also be aware, some transitions do not work well with each other and it is up to you to find something that is pleasing.

# Overriding CSS Transition
Say you want a different `transition-duration` or `transition-timing-function` all you need to do is override it in the `style` for the `QFlashcardSection`. For example, the `slide-*` transitions have a default time of `.3s`. If you wanted to change it to 1 second, you would do it like this:
```html
<q-flashcard-section transition="slide-up-in" style="transition: all 1s ease-in-out !important;">
```

# Questions
- Q. Can I use my own transitions?
- A. Yes, you can! Make your transition and the styling must be prefixed with `fc-`, for example `.fc-my-transition` and then for the `transition` property of `QFlashcardSection` call it like this: `transition="my-transition"`. The `fc-` is automatically prefixed to the tansition name. However, it must fall under the `.q-flashcard` namespace, as in:
  ```stylus
  .q-flashcard .fc-my-transition {
    /* attribuutes */
  }
  ```
  This is so the transition only works while in a QFlashcard area as these transitons should not be used with other elements/compnents.
- Q. Why prefix with `'fc-'`?
- A. This is to avoid name style collisions. Having a transition called `.slide-out` would be too generic. Having `.fc-slide-out` is more deterministic.

# Patreon
If you like (and use) this App Extension, please consider becoming a Quasar [Patreon](https://www.patreon.com/quasarframework).
