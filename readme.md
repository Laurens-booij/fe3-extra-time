# Fed 3 data - Extra time
## Intro
For the subject `Frontend development 3 data` I did a few extra things to further my personal development.  This was a part of the curriculum.

## What did I do?
Below, I listed al the things that I did:

###

### d3.queue()
For `Assessment 3` I used a dataset that consisted of ten different files. In order to load al these files, I learned how to use the `d3.queue()` function. I used [the d3.queue git page][d3.queue] as a source for learning how to use it. The code that I ended up writing looks as follows:

```javascript
// Get all files using a callback //
d3.queue()
    .defer(d3.text, "data/einsteinweg.txt")         // load file
    .defer(d3.text, "data/haarlemmerweg.txt")
    .defer(d3.text, "data/JanVanGalenstraat.txt")
    .defer(d3.text, "data/kantershof.txt")
    .defer(d3.text, "data/nieuwendammerdijk.txt")
    .defer(d3.text, "data/ookmeer.txt")
    .defer(d3.text, "data/oudeSchans.txt")
    .defer(d3.text, "data/stadhouderskade.txt")
    .defer(d3.text, "data/vanDiemenstraat.txt")
    .defer(d3.text, "data/vondelpark.txt")
    .awaitAll(function(error, files){               // Waits for all files to load and then store them in an array, accesible as parameter `files`

      var doc = files.join();                       // joins the elements from array `files` together to form a string
    })
```

### Explained javascript to my mother in law
I showed the end result of my [Assessment 3 assignment][assesment 3] to my mother in law. I ended up explaining all the code to her. She has no experience with programming or writing code at all. In the end she knew the following things:
* What a `variable` was.
* What an `array` was and that it starts with `0` as the first `index number`.
* What a `function` is and how its called.
* What a `parameter` is and how it is passed on to a `function`.
* How `attributes` are added to elements using `.attr()`.

On top of these things, I explained a lot of other things along the way. In the end she had a general idea of how my code worked, as well as a good understanding of the things that are listed above.

By explaining my code, I enhanced my understanding of it.

### Learned to write a mapping function
I learned how to write my own mapping function that maps a value between `0 and 100` to the right `pixel value`. This also takes the actual pixel dimensions of the container into account. I looked at various examples on the internet in order to learn how to do it.

The code I have written as a result is written entirely by me and looks as follows:

```javascript
var mapWidth = document.querySelector(".map-container").offsetWidth;   // get actual width of `.map-container`
var mapHeight = document.querySelector(".map-container").offsetHeight; // get actual height of `.map-container`

// map value between 0 and 100 to a value between 0 and `mapWidth`
var mapX = d3.scaleLinear()
               .domain([0, 100 ])           // input is a value from 0 to 100
               .range([0, mapWidth]);       // map the given value to a value between 0 and `mapWidth`

// map value between 0 and 100 to a value between 0 and `mapHeight`
var mapY = d3.scaleLinear()
               .domain([0, 100 ])
               .range([0, mapHeight]);
```


[d3.queue]: https://github.com/d3/d3-queue
[assesment 3]: https://github.com/Laurens-booij/fe3-assessment-3
