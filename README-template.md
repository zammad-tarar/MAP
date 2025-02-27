# Frontend Mentor - IP Address Tracker Solution

This is my solution to the [IP Address Tracker challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/ip-address-tracker-I8-0yYAH0). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of Contents

- [Overview](#overview)
  - [The Challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My Process](#my-process)
  - [Built With](#built-with)
  - [What I Learned](#what-i-learned)
  - [Continued Development](#continued-development)
  - [Useful Resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The Challenge

The challenge was to build an IP Address Tracker application that allows users to:

- View their own IP address and location on the map upon initial page load.
- Search for any IP address or domain and see the key information (IP address, location, timezone, and ISP).
- See the optimal layout for the site depending on their device's screen size.
- See hover states for all interactive elements on the page.

### Screenshot

![Desktop Preview](./screenshots/desktop-preview.png)
![Mobile Preview](./screenshots/mobile-preview.png)

**Note:** Add your own screenshots of the solution. You can use tools like [FireShot](https://getfireshot.com/) or your browser's built-in screenshot feature.

### Links

- **Solution URL:** [Frontend Mentor Solution](https://www.frontendmentor.io/solutions/your-solution-url)
- **Live Site URL:** [Live Site](https://your-live-site-url.com)

## My Process

### Built With

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile-first workflow
- [LeafletJS](https://leafletjs.com/) - For interactive maps
- [IP Geolocation API by IPify](https://geo.ipify.org/) - For IP address data

### What I Learned

While working on this project, I learned:

- How to integrate third-party APIs (IPify) to fetch and display real-time data.
- How to use LeafletJS to create and manipulate interactive maps.
- How to handle form submissions and dynamically update the DOM with JavaScript.
- The importance of responsive design and ensuring the layout works across all screen sizes.

Here’s a code snippet I’m proud of:

```javascript
async function fetchIPData(ip = '') {
  const apiKey = 'YOUR_API_KEY';
  const url = `https://geo.ipify.org/api/v2/country,city?apiKey=${apiKey}&ipAddress=${ip}`;

  try {
    const response = await fetch(url);
    const data = await response.json();
    updateUI(data);
  } catch (error) {
    console.error('Error fetching IP data:', error);
  }
}