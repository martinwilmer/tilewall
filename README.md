# jQuery tileWall

A jQuery Plugin for the dynamically positioning of tiles in a responsive grid.


## Usage

1. Include jQuery:

```
<script src="http://ajax.googleapis.com/ajax/libs/jquery/2.0.0/jquery.min.js"></script>
```

2. Include plugin's code:

```
<script src="dist/jquery.tilewall.min.js"></script>
```

3. Call the plugin:

```
$("#tilewall").tileWall(options);
```


## Sample HTML

```
<div id="tilewall">
	<div class="tile" data-width="1" data-height="1" data-priority="1">Cute cats</div>
	<div class="tile" data-width="3" data-height="2" data-priority="1">Beer</div>
	<div class="tile" data-width="2" data-height="4" data-priority="1">Everything else</div>
</div>
```


## Navigation tiles

Use attribute and value `data-nav="1"` to define a navigation tile.
The algorithm will automatically try to place navigation tiles in higher
positions of the grid to be easily seen by users.

```
<div class="tile" data-width="1" data-height="1" data-nav="1">Contact form</div>
```


## Fix positioned tiles

Use attributes `data-position-x` and `data-position-y` to define a static tile in the grid.
If the attribute values are out of grid size (e.g. on small viewports), they are disregarded.

```
<div class="tile" data-width="1" data-height="1" data-priority="1" data-position-x="2" data-position-y="3">Content</div>
```


## Options

- `debounceTime: int` min milliseconds between two resize events to refresh the
tile positioning (*default: 100*)
- `debug: [1|0]` enable/disable debug logging in the console (*default: 0*)
- `hideNavTilesOnViewportWidthSmallerThan: int(px)` if > 0, hide navigation tiles on
viewports less wide than the given pixels (*default: 0*)
- `maxNumCols: int` the maximum number of columns the grid (*default: 12*)
- `minNumCols: int` the minimum number of columns the grid (*default: 3*)
- `minTileWidth: int(px)` the minimum width of a tile with `data-width="1"` (*default: 130*)
- `shrinkTilesOnViewportWidthSmallerThan: int(px)` if > 0, shrink all tiles to 1x1 size on
viewports less wide than the given pixels (*default: 0*)
- `tileClassName: string`: class name of dom elements that shall be used as tiles
(*default: "tile"*)
- `tileMargin: int(px)` horizontal and vertical margin of tiles (*default: 2*)
- `transition: [1|0]` enable/disable css transitions on tiles (*default: 0*)


## Demo

[http://tilewall.martinwilmer.com](http://tilewall.martinwilmer.com)


## Todo

- lots of refactoring
- validating passed options
- awesome css transitions
- option to fill gaps by repeating (small) tiles
- bug: The tileWall wrapper has no initial height. The scrollbar width cannot be
regarded in the first run. Current hack: calling reformatTiles() twice on the first run.
- document priority attribute
