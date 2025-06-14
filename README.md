
<h1>Andrew Tate's Github Page</h1>
Hi, I'm a senior CS major from Whitman College and this is a Github pages pages
for my Data Science Class!

<h2>Data Science Final Project</h2>
<a href="https://tater-tot25.github.io/DataScienceFinalProject/" target="_blank">Link</a>

<h2>Ideas for Data Science Project</h2>
1. Drinking and Driving:
    * We would figure out the most popular alcohol to drive on
    * How many people die compared to sober drivers
    * How many kids die in drunk driving related accidents
    * Other fun statistics
    [Link](https://www.kaggle.com/datasets/bryanmaloney/dui-arrests-and-population-by-state-2015-usa)
    [Link](https://www.kaggle.com/datasets/linzey/alcohol-consumption-us)
2. Surfing:
    * What board do high performance surfers 
    * What is the ideal wave type
    * Cross reference this with a weather dataset and find the ideal conditions for those qualities
    [Link](https://www.kaggle.com/datasets/loureiro85/surfing)
3. Best Places to Bartend:
    * Where do people order the most diverse drinks
    * Where do people prefer spirits to other types of alcohol
    * cross reference this with average pay and work hours from a different dataset
    [Link](https://www.kaggle.com/datasets/mysarahmadbhat/alcohol-consumption)
4. Worst Places to work in the CS industry
    * What state pays the worst and best overall for any job
    * See if this corresponds to software developers
    [Link](https://www.kaggle.com/datasets/thedevastator/u-s-software-developer-salaries)
5. Professor Beauty and Rankings
    * I found a dataset that ranks professor beauty.
    * See if beauty increases with the score of the professor. 
    [Link](https://www.openintro.org/data/index.php?data=evals)

<h2>Where's Schueller?</h2>
This is a figure from the assigment where I tried to figure out where Schueller prefers
to go out to drink.
{% include figure.html %}

<h2>Above and Beyond</h2>
For my above and beyond I have embeded snake
{% include snake.html %}

<h2>Other Work</h2>
These are some games I've developed
<iframe frameborder="0" src="https://itch.io/embed/2271908?bg_color=3f3f3f&amp;fg_color=cbb6a9&amp;link_color=bf5e38&amp;border_color=6f6c6b" width="552" height="167"><a href="https://andrew-wilson.itch.io/static-sanctuary">Static Sanctuary by Tater-Tot</a></iframe>
<iframe frameborder="0" src="https://itch.io/embed/2420081?bg_color=dbbec0&amp;fg_color=000000&amp;link_color=e29066&amp;border_color=8cb832" width="552" height="167"><a href="https://andrew-wilson.itch.io/mowed">moWed by Tater-Tot</a></iframe>
<iframe frameborder="0" src="https://itch.io/embed/2070426?bg_color=743896&amp;fg_color=fce0ff&amp;link_color=76f9fa&amp;border_color=8a3db2" width="552" height="167"><a href="https://andrew-wilson.itch.io/space-exploration-vr">Space Exploration VR (Temporary Title) by Tater-Tot</a></iframe>

<h2>Current Tap List</h2>
<div id="beer-menu" style="display: flex; flex-wrap: wrap; gap: 1em; justify-content: center;"></div>

<script>
const apiUrl = "https://script.google.com/macros/s/AKfycbz7bLjFjF_doYOu-A6SXU98tJpTB8FnC0Pq1oK8vsUuAAUSbFKUkE7hvevyBNTvIgI/exec";

fetch(apiUrl)
  .then(res => res.json())
  .then(beers => {
    const container = document.getElementById("beer-menu")

    beers.forEach(beer => {
      const card = document.createElement("div");
      card.style = `
        background: white;
        border-radius: 10px;
        box-shadow: 0 2px 6px rgba(0,0,0,0.1);
        padding: 1em;
        max-width: 300px;
        flex: 1 1 200px;
        font-family: sans-serif;
      `;

      card.innerHTML = `
        <div style="font-weight: bold; font-size: 1.2em;">${beer.Name}</div>
        <div><strong>Type:</strong> ${beer.Type}</div>
        <div><strong>ABV:</strong> ${beer.ABV }<strong>%</strong></div>
        <div><strong>Brewery:</strong> ${beer.Brewery}</div>
        <div><strong>Location:</strong> ${beer.Location}</div>
      `;

      container.appendChild(card);
    });
  })
  .catch(error => {
    document.getElementById("beer-menu").textContent = "Failed to load beer menu.";
    console.error("Error:", error);
  });
</script>
