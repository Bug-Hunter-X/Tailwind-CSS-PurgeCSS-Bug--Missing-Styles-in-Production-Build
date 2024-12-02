# Tailwind CSS PurgeCSS Bug: Missing Styles in Production

This repository demonstrates an uncommon bug encountered with Tailwind CSS's PurgeCSS feature.  In certain production builds, specific styles defined in the Tailwind CSS configuration are purged despite being used in the application.  The issue only occurs intermittently and is difficult to reproduce consistently.

## Bug Reproduction

1. Clone the repository.
2. Run `npm install` to install project dependencies.
3. Run `npm run build` to build the application.
4. Observe missing styles in the production build.

The issue is likely related to how PurgeCSS analyzes the application's code during the build process.  It may be incorrectly identifying unused styles or failing to correctly track the usage of dynamic classes.

## Solution

The solution involves refining PurgeCSS configuration to ensure that all necessary styles are preserved during the purging process. This may include adjusting the `content` option to explicitly include all files that use Tailwind CSS classes, or using a more robust strategy to handle dynamic classes.