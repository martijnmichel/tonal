# music-scale [![npm version](https://img.shields.io/npm/v/music-scale.svg)](https://www.npmjs.com/package/music-scale)

[![tonal](https://img.shields.io/badge/tonal-music--scale-yellow.svg)](https://www.npmjs.com/package/tonal)

`music-scale` is a function to create music scales with ease:

```js
var scale = require('music-scale')
var major = scale('1 2 3 4 5 6 7')
major('A') // => ['A', 'B', 'C#' 'D', 'E', 'F#', 'G#']
```

This is part of [tonal](https://www.npmjs.com/package/tonal)

## Install

Via npm: `npm i --save music-scale`

## Usage

#### Create scales

Scales are a pitch sets with a tonic. Scales can be created from a list of intervals and a tonic:

```js
scale('1 2 3m 4 5 6m 7', 'D') // => ['D', 'E', 'F', 'G', 'A', 'Bb', 'C#']
```

This function can be partially applied:

```js
var dorian = set('1 2 3b 4 5 6 7b')
dorian('eb') // => [ 'Eb', 'F', 'Gb', 'Ab', 'Bb', 'C', 'Db' ]
```

The source can be also another scale:

```js
scale('C D E F G A B C', 'A') // => ['A', 'B', 'C#' 'D', 'E', 'F#', 'G#']
```

Or even a collection of notes:

```js
scale('C2 d4 g7 a2', 'C') // => ['C', 'D', 'G', 'A']
```

#### Scale tonics

If the tonic of a scale is a pitch class (a note without octave) the notes of the scale are pitch classes:

```js
var major = scale('C D E F G A B C')
major('A') // => ['A', 'B', 'C#' 'D', 'E', 'F#', 'G#']
```

If the tonic of the scale is a note with octave, the notes of the scale will have octave numbers:

```js
major('A4') // => ['A4', 'B4', 'C#5' ,'D5', 'E5', 'F#5', 'G#5']
```

If the tonic of a scale is false, the intervals are returned:

```js
major(false) // => ['P1', 'M2', 'M3', 'P4', 'P5', 'M6', 'M7']
```

Finally, if the tonic is null and the source are notes, the first pitch class of the scale source will be the tonic:

```js
major(null) // => ['C', 'D', 'E', 'F', 'G', 'A', 'B']
scale('d4 f5 g2 c6 a1', null) // => [ 'D', 'F', 'G', 'A', 'C' ]
```

## License

MIT License