# Security Policy

## Reporting a vulnerability

Please report suspected vulnerabilities privately, using the **Report a vulnerability** button on the Security tab of this repository. If that button is not there, or you would rather not go through GitHub, email david.anderson@excelano.com instead. I aim to respond within seven days.

Please do not open public issues for security problems.

## Supported versions

The latest release receives security fixes. Older versions are not supported. Vier is distributed as source, so a fix reaches you when you build from the latest `main`.

## What Vier can access

Vier makes no network request, opens no socket and links no networking or analytics code. It requests no entitlements beyond the defaults, so it cannot reach contacts, location, health data, the microphone or anything else on the iPhone or the watch. The iPhone and watch apps do not talk to each other.

## What Vier stores

The chosen difficulty, the players setting, the game in progress and who moves first next are kept in each app's own preferences on its device, and removing the app removes them.
