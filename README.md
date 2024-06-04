# Basketball Smart Referee

Welcome to the **Basketball Smart Referee** project! This README will guide you through the project's purpose, implementation details, usage, and show te results of our method.

**Team:**
- Donovan Sanders
- Andrew Cen
- Alex Trevithick

---

## Table of Contents

1. [Abstract](#abstract)
2. [Installation](#installation)
3. [Usage](#usage)
4. [Video/Image Results](#videoimage-results)
5. [Reproduction Details](#reproduction-details)
6. [Contributing](#contributing)
---


## Abstract

In this repo, we present the results and code for our project on creating an automated referee for pickup basketball games. Assuming a single-view camera setup, we present a method to quickly detect made shots and the team of the scorer (assuming black/white uniforms). In order to accomplish this, we leverage a YoLo model finetuned for basketball, human, and rim detection from [RoboFlow](https://universe.roboflow.com/roboflow-universe-projects/basketball-players-fy4c2). Using the 2D tracking of the ball and the rim, we can calculate a 2D linear approximation of the ball trajectory and check if it intersects the correct area of the rim to make a point, along with other heuristics to ensure proper point counting including the cosine similarity of the rim with the ball trajectory along with checks on the ball height. Simultaneously, we leverage the SoTA [FastSAM](https://github.com/CASIA-IVA-Lab/FastSAM) model, for real-time segmentation of the players clothing. Using the detected pixels for both players bounding boxes, we can threshold the pixel intensity or check which player has a darker shirt. Note that our solution does not require training per game, and naturally generalizes due to the large-scale priors leveraged in our work.

![WebPresence Logo](media/shots.gif)

---

## Features

- **Analytics Dashboard:** Get comprehensive insights into your website's traffic and performance.
- **SEO Optimization:** Receive tips and suggestions to improve your site's SEO.
- **Responsive Design:** Ensure your website looks great on all devices.
- **Custom Reports:** Generate custom reports based on your specific needs.

---

## Installation

To install WebPresence, follow these steps:

1. **Clone the repository:**
    ```bash
    git clone https://github.com/yourusername/webpresence.git
    ```
2. **Navigate to the project directory:**
    ```bash
    cd webpresence
    ```
3. **Install the required dependencies:**
    ```bash
    npm install
    ```

---

## Usage

### Running the Application

To start the application, use the following command:

```bash
npm start
