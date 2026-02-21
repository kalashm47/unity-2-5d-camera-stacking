# Unity 2.5D Camera Stacking Demo

A small technical project demonstrating how to correctly mix **2D sprites** inside a **3D environment** using Camera Stacking in Unity 6 (URP).

This repository was created as a learning and teaching resource and accompanies a video tutorial explaining the full setup step-by-step.

---

## Overview

This project shows how to build a clean 2.5D structure by separating rendering, physics and visuals into independent systems.

The main goal is to solve common problems when mixing 2D and 3D:

* Incorrect rendering order
* Sprites appearing behind 3D objects
* Perspective distortion
* Flat sprites revealing their sides when the camera rotates

The solution uses:

* Camera Stacking
* Layer separation
* Billboard rotation
* Modular player architecture

---

## Screenshot

<img width="627" height="433" alt="image" src="https://github.com/user-attachments/assets/1d5f3a25-7e1d-4166-9be1-48e2bd80094a" />


You can upload images to the repository and place them inside a `Screenshots` folder, then link them like this:

![Gameplay](Screenshots/screenshot1.png)
![Camera Setup](Screenshots/screenshot2.png)

---

## Features

* 3D environment rendered by a Base Camera
* 2D character rendered by an Overlay Camera
* Billboard system to keep the sprite facing the camera
* Layer-based rendering separation (World3D / Sprite2D)
* Modular player structure (Logic / Visual / Collision)
* Example player movement controller

---

## Project Structure

The player is divided into three different GameObjects:

**Player**

* Handles movement and logic

**Visual**

* Contains the SpriteRenderer
* Holds the Billboard script

**Collisions**

* Contains the Capsule Collider and physics components

This separation prevents visual rotation from affecting physics or movement.

---

## How Camera Stacking Works

The project uses two cameras:

**Base Camera**

* Renders the 3D world
* Only sees the `World3D` layer

**Overlay Camera**

* Renders the 2D character
* Only sees the `Sprite2D` layer

The Overlay camera is added to the Base camera stack, allowing the sprite to render on top of the environment.

---

## Billboard System

Since the character is a flat sprite inside a 3D world, it would normally reveal its side when the camera rotates.

The Billboard script forces the sprite to always align with the camera direction during `LateUpdate`, preserving the 2.5D illusion.

---

## Requirements

* Unity 6
* Universal Render Pipeline (URP)

---

## How to Open

1. Clone the repository
2. Open Unity Hub
3. Click "Add project"
4. Select the project folder
5. Open using Unity 6

Unity will automatically import the required packages.

---

## Tutorial Video

*(Place your YouTube link here)*

---

## Learning Purpose

This project is intended for:

* Beginners learning Unity rendering
* Developers interested in 2.5D games
* Anyone wanting to understand Camera Stacking in practice

---

## License

Free to use for learning and educational purposes.
