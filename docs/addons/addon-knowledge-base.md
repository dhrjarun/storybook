---
title: Addon knowledge base
---

Once you understand the basics of writing addons, there are a variety of common enhancements to make your addon better. This page details additional information about addon creation. Use it as a quick reference guide when creating your own addons.

### Disable the addon panel

It’s possible to disable the addon panel for a particular story.

To make that possible, you need to pass the `paramKey` element when you register the panel:

<!-- prettier-ignore-start -->

<CodeSnippets
  paths={[
    'common/storybook-addon-disable-addon.js.mdx',
  ]}
/>

<!-- prettier-ignore-end -->

Then when adding a story, you can pass a disabled parameter.

<!-- prettier-ignore-start -->

<CodeSnippets
  paths={[
    'common/button-story-disable-addon.js.mdx',
  ]}
/>

<!-- prettier-ignore-end -->

### Style your addon

Storybook uses [Emotion](https://emotion.sh/docs/introduction) for styling. Alongside with a theme that you can customize!

We recommend using Emotion to style your addon’s UI components. That allows you to use the active Storybook theme to deliver a seamless developer experience.
If you don’t want to use Emotion, you can use inline styles or another css-in-js lib. You can receive the theme as a prop by using Emotion's `withTheme` HOC. [Read more about theming](../configure/theming.md).

### Storybook components

Addon authors can develop their UIs using any React library. But we recommend using Storybook’s UI components in `@storybook/components` to build addons faster. When you use Storybook components, you get:

- Battle-tested off-the-shelf components
- Storybook native look and feel
- Built-in support for Storybook theming

Use the components listed below with your next addon.

| Component          | Source                                                                                                                                            | Story                                                                                                                          |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Action Bar         | [See component implementation](https://github.com/storybookjs/storybook/blob/main/code/ui/components/src/ActionBar/ActionBar.tsx)                 | [See component story](https://main--5a375b97f4b14f0020b0cda3.chromatic.com/?path=/story/basics-actionbar--single-item)         |
| Addon Panel        | [See component implementation](https://github.com/storybookjs/storybook/blob/main/code/ui/components/src/addon-panel/addon-panel.tsx)             | N/A                                                                                                                            |
| Badge              | [See component implementation](https://github.com/storybookjs/storybook/blob/main/code/ui/components/src/Badge/Badge.tsx)                         | [See component story](https://main--5a375b97f4b14f0020b0cda3.chromatic.com/?path=/story/basics-badge--all-badges)              |
| Button             | [See component implementation](https://github.com/storybookjs/storybook/blob/main/code/ui/components/src/Button/Button.tsx)                       | [See component story](https://main--5a375b97f4b14f0020b0cda3.chromatic.com/?path=/story/basics-button--all-buttons)            |
| Form               | [See component implementation](https://github.com/storybookjs/storybook/blob/main/code/ui/components/src/form/index.tsx)                          | [See component story](https://main--5a375b97f4b14f0020b0cda3.chromatic.com/?path=/story/basics-form-button--sizes)             |
| Loader             | [See component implementation](https://github.com/storybookjs/storybook/blob/main/code/ui/components/src/Loader/Loader.tsx)                       | [See component story](https://main--5a375b97f4b14f0020b0cda3.chromatic.com/?path=/story/basics-loader--progress-bar)           |
| PlaceHolder        | [See component implementation](https://github.com/storybookjs/storybook/blob/main/code/ui/components/src/placeholder/placeholder.tsx)             | [See component story](https://main--5a375b97f4b14f0020b0cda3.chromatic.com/?path=/story/basics-placeholder--single-child)      |
| Scroll Area        | [See component implementation](https://github.com/storybookjs/storybook/blob/main/code/ui/components/src/ScrollArea/ScrollArea.tsx)               | [See component story](https://main--5a375b97f4b14f0020b0cda3.chromatic.com/?path=/story/basics-scrollarea--vertical)           |
| Space              | [See component implementation](https://github.com/storybookjs/storybook/blob/main/code/ui/components/src/spaced/Spaced.tsx)                       | [See component story](https://main--5a375b97f4b14f0020b0cda3.chromatic.com/?path=/story/basics-spaced--row)                    |
| Syntax Highlighter | [See component implementation](https://github.com/storybookjs/storybook/blob/main/code/ui/components/src/syntaxhighlighter/syntaxhighlighter.tsx) | [See component story](https://main--5a375b97f4b14f0020b0cda3.chromatic.com/?path=/story/basics-syntaxhighlighter--bash)        |
| Tabs               | [See component implementation](https://github.com/storybookjs/storybook/blob/main/code/ui/components/src/tabs/tabs.tsx)                           | [See component story](https://main--5a375b97f4b14f0020b0cda3.chromatic.com/?path=/story/basics-tabs--stateful-static)          |
| ToolBar            | [See component implementation](https://github.com/storybookjs/storybook/blob/main/code/ui/components/src/bar/bar.tsx)                             | N/A                                                                                                                            |
| ToolTip            | [See component implementation](https://github.com/storybookjs/storybook/blob/main/code/ui/components/src/tooltip/Tooltip.tsx)                     | [See component story](https://main--5a375b97f4b14f0020b0cda3.chromatic.com/?path=/story/basics-tooltip-tooltip--basic-default) |
| Zoom               | [See component implementation](https://github.com/storybookjs/storybook/blob/main/code/ui/components/src/Zoom/Zoom.tsx)                           | [See component story](https://main--5a375b97f4b14f0020b0cda3.chromatic.com/?path=/story/basics-zoom--element-actual-size)      |

Complementing the components, also included is a set of UI primitives. Use the content listed below as a reference for styling your addon.

| Component                      | Source                                                                                                         | Story                                                                                                    |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Color Palette (see note below) | [See implementation](https://github.com/storybookjs/storybook/tree/master/code/ui/components/src/Colors)       | [See story](https://main--5a375b97f4b14f0020b0cda3.chromatic.com/?path=/story/basics-colorpalette--page) |
| Icon                           | [See implementation](https://github.com/storybookjs/storybook/blob/main/code/ui/components/src/icon/icons.tsx) | [See story](https://main--5a375b97f4b14f0020b0cda3.chromatic.com/?path=/story/basics-icon--labels)       |
| Typography                     | [See implementation](https://github.com/storybookjs/storybook/tree/master/code/ui/components/src/typography)   | [See story](https://main--5a375b97f4b14f0020b0cda3.chromatic.com/?path=/story/basics-typography--all)    |

<div class="aside">
The color palette implemented by <code>@storybook/components</code> is a high-level abstraction of the <a href="https://github.com/storybookjs/storybook/tree/next/code/lib/theming/src"><code>@storybook/theming</code></a> package.
</div>

### Build system

When you're developing your addon as a package, you can’t use `npm link` to add it to your project. List your addon as a local dependency into your package.json:

```json
{
  "dependencies": {
    "@storybook/addon-controls": "file:///home/username/myrepo"
  }
}
```

<div class="aside">
Run either <code>yarn</code> or <code>npm install</code> to install the addon.
</div>

### Hot module replacement

While developing your addon, you can configure HMR (hot module replacement) to reflect the changes made.

### Standalone Storybook addons

If you're developing a standalone addon, add a new script to `package.json` with the following:

```json
{
  "scripts": {
    "start": "npm run build -- --watch"
  }
}
```

#### Local Storybook addons

If you're developing a local Storybook addon built on top of an existing Storybook installation, HMR (hot module replacement) is available out of the box.

If you don't see the changes being reflected, add the flag `--no-manager-cache` to the `storybook` script and restart Storybook.

### Composing addons in presets

If you're working on a preset that loads third-party addons, which you don't have control over, and you need access to certain features (e.g., decorators) or provide additional configurations. In that case, you'll need to update your preset to the following to allow you to load and configure the other addons:

<!-- prettier-ignore-start -->

<CodeSnippets
  paths={[
    'common/storybook-addon-load-external-addons-preset.js.mdx',
  ]}
/>

<!-- prettier-ignore-end -->

If you have control over the addons you want to customize. In that case, you can update your preset and implement a custom function to load any additional presets and provide the necessary configuration, similar to how it's implemented in the [Essentials](../../addons/essentials/src/index.ts) addon.
