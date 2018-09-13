# UnityXcodeCache

Simply setup cache for Unity generated Xcode project to speed up build times.

## Usage

1. Clone repository into Unity `Editor` folder.
2. Execute `Tools/Xcode/WriteCache` before build Xcode project.
3. Build Xcode project.
4. Execute `Tools/Xcode/ReadCache` after build Xcode project.
5. Open Xcode and build, build will use previous build cache to speed up

## Introduction

The principle is simple:

1. Copy whole Xcode project to `Cache` folder and preserve all timestamps. Cause Xcode use file and directory timestamp to decide whether to use cache.
2. Use Unity to generate Xcode project
3. Depth-first traverse Xcode project and compare file with cached, set timestamp to cached if they are equal.

## Environment

- Unity 2017.4.2f2
- Xcode 9.4.1
- macOS 10.13.6

It didn't use any special trick, so it should compatible with all Unity, macOS and Xcode versions.
