# Interactive Rating Component
Implementation of [Interactive Rating Component](https://www.frontendmentor.io/challenges/interactive-rating-component-koxpeBUmI) using Vue and TailwindCSS. This project makes use of event emitters, component props and local state. 

## Initial State - No Rating Selected
The app loads with a blank rating screen and no rating options selected. 
The submission button is also greyed out and non-clickable. When a rating is hovered over, the option
is highlighted in a lighter gray color. 

<img src="./src/assets/readme/no-rating.png" style="width: 300px; display:inline; padding: 10px;">
<img src="./src/assets/readme/no-rating-highlight.png" style="width: 300px; display:inline;">

## Middle State - Rating Selected
Once a rating has been selected, its background changes
to orange and the submit button becomes active. Once the
button is active, hovering over it changes it to an active style. 

<img src="./src/assets/readme/rating-chosen.png" style="width: 300px; display:inline; padding: 10px;">
<img src="./src/assets/readme/rating-chosen-submit.png" style="width: 300px; display:inline;">

## Final State - Rating Submitted
Once the submit button has been clicked, rating card transitions out using a slide and fade into the thank-you card, with the user's rating in the card callout. 

<img src="./src/assets/readme/rating-submitted.png" style="width: 300px; display:inline; padding: 10px;">