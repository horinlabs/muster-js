# MusterJS
Muster is the definitive way to work with collections in Javascript.

How to install:

`npm install muster-js`

Example of use:

```
var collect = require('muster-js').collect;

var collection = collect([
	{ id: 1, name: 'Bulbasaur', type: 'grass' },
	{ id: 4, name: 'Charmander', type: 'fire' },
	{ id: 7, name: 'Squirtle', type: 'blue' }
]);

collection.count(); //outputs 3
collection.get(2).name; //outputs 'Squirtle'
```

Most of methods return a new collection, so you can chain the calls if you want:
```
var collect = require('muster-js').collect;

var collection = collect([
	{ id: 1, name: 'Bulbasaur', type: 'grass' },
	{ id: 4, name: 'Charmander', type: 'fire' },
	{ id: 7, name: 'Squirtle', type: 'water' }
]);

collection
	.union([
		{ id: 152, name: 'Chikorita', type: 'grass' },
		{ id: 155, name: 'Cindaquil', type: 'fire' },
		{ id: 158, name: 'Totodile', type: 'water' }
	])
	.where('type', 'water')
	.all(); //outputs '[{ id: 7, name: 'Squirtle', type: 'water' }, { id: 158, name: 'Totodile', type: 'water' }]'
```

* * *
## API documentation

### all()

Get all of the items in the collection.

**Returns**: `Array`

### avg(callback)

Get the average value of a given key.

**Parameters**

**callback**: `string | function`

**Returns**: `*`

### chunk(size)

Chunk the underlying collection array.

**Parameters**

**size**: `int`

**Returns**: `Collection`

### collapse()

Collapse the collection of items into a single array.

**Returns**: `Collection`

### combine(values)

Create a collection by using this collection for keys and another for its values.

**Parameters**

**values**: `*`

**Returns**: `Collection`

### contains(key, value)

Determine if an item exists in the collection.

**Parameters**

**key**: `*`

**value**: `*`

**Returns**: bool

### containsStrict(key, value)

Determine if an item exists in the collection using the strict mode.

**Parameters**

**key**: `*`

**value**: `*`

**Returns**: bool

### count()

Count the number of items in the collection.

**Returns**: int

### diff(items)

Get the items in the collection that are not present in the given items.

**Parameters**

**items**: `*`

**Returns**: `Collection`

### each(callback)

Execute a callback over each item.

**Parameters**

**callback**: `function`

**Returns**: this

### every(step, offset)

Create a new collection consisting of every n-th element.

**Parameters**

**step**: `int`

**offset**: `int`

**Returns**: `Collection`

### except(keys)

Get all items except for those with the specified keys.

**Parameters**

**keys**: `*`

**Returns**: `Collection`

### filter(callback)

Run a filter over each of the items.

**Parameters**

**callback**: `function | null`

**Returns**: `Collection`

### first(callback, default)

Get the first item from the collection.

**Parameters**

**callback**: `function | null`

**default**: `*`

**Returns**: `*`

### flatten(depth)

Get a flattened array of the items in the collection.

**Parameters**

**depth**: `int`

**Returns**: `Collection`

### flip()

Flip the items in the collection.

**Returns**: `Collection`

### forget(keys)

Remove an item from the collection by key.

**Parameters**

**keys**: `string | array`

**Returns**: this

### forPage(page, perPage)

"Paginate" the collection by slicing it into a smaller collection.

**Parameters**

**page**: `int`

**perPage**: `int`

**Returns**: `Collection`

### get(key, callback)

Get an item from the collection by key.

**Parameters**

**key**: `int`

**callback**: `*`

**Returns**: `*`

### groupBy(groupBy, preserveKeys)

Group an associative array by a field or using a callback.

**Parameters**

**groupBy**: `function | string`

**preserveKeys**: `bool`

**Returns**: `Collection`

### has(key)

Determine if an item exists in the collection by key.

**Parameters**

**key**: `*`

**Returns**: bool

### implode(value, glue)

Concatenate values of a given key as a string.

**Parameters**

**value**: `string`

**glue**: `string`

**Returns**: string

### intersect(items)

Intersect the collection with the given items.

**Parameters**

**items**: `*`

**Returns**: `Collection`

### isEmpty()

Determine if the collection is empty or not.

**Returns**: bool

### keyBy(keyBy)

Key an associative array by a field or using a callback.

**Parameters**

**keyBy**: `function | string`

**Returns**: `Collection`

### keys()

Get the keys of the collection items.

**Returns**: `Collection`

### last(callback, default)

Get the last item from the collection.

**Parameters**

**callback**: `function | null`

**default**: `*`

**Returns**: `*`

### map(callback)

Run a map over each of the items.

**Parameters**

**callback**: `function`

**Returns**: `Collection`

### max(key)

Get the max value of a given key.

**Parameters**

**key**: `string | null`

**Returns**: `*`

### median(null)

Get the median of a given key.

**Parameters**

**null**: key

**Returns**: `*`

### merge(items)

Merge the collection with the given items.

**Parameters**

**items**: `*`

**Returns**: `Collection`

### min(key)

Get the min value of a given key.

**Parameters**

**key**: `string | null`

**Returns**: `*`

### mode(key)

Get the mode of a given key.

**Parameters**

**key**: `string | null`

**Returns**: `Array`

### pipe(callback)

Pass the collection to the given callback and return the result.

**Parameters**

**callback**: `function`

**Returns**: `*`

### pluck(value)

Get the values of a given key.

**Parameters**

**value**: `string`

**Returns**: `Collection`

### pop()

Get and remove the last item from the collection.

**Returns**: `*`

### prepend(value, key)

Push an item onto the beginning of the collection.

**Parameters**

**value**: `*`

**key**: `*`

**Returns**: this

### pull(key)

Get and remove an item from the collection.

**Parameters**

**key**: `*`

**Returns**: this

### push(value)

Push an item onto the end of the collection.

**Parameters**

**value**: `*`

**Returns**: this

### random(amount)

Get one or more items randomly from the collection.

**Parameters**

**amount**: `int`

**Returns**: `*`

### reduce(callback, initial)

Reduce the collection to a single value.

**Parameters**

**callback**: `function`

**initial**: `*`

**Returns**: `*`

### reject(callback)

Create a collection of all elements that do not pass a given truth test.

**Parameters**

**callback**: `function`

**Returns**: `Collection`

### reverse()

Reverse items order.

**Returns**: `Collection`

### search(value, strict)

Search the collection for a given value and return the corresponding key if successful.

**Parameters**

**value**: `*`

**strict**: `bool`

**Returns**: `*`

### shift()

Get and remove the first item from the collection.

**Returns**: `*`

### shuffle()

Shuffle the items in the collection.

**Returns**: `Collection`

### slice(offset, length)

Slice the underlying collection array.

**Parameters**

**offset**: `int`

**length**: `int`

**Returns**: `Collection`

### sort(callback)

Sort through each item with a callback.

**Parameters**

**callback**: `function | null`

**Returns**: `Collection`

### sortBy(callback, options, descending)

Sort the collection using the given callback.

**Parameters**

**callback**: `function | string`

**options**: `int`

**descending**: `bool`

**Returns**: `Collection`

### sortByDesc(callback, options)

Sort the collection in descending order using the given callback.

**Parameters**

**callback**: `function | string`

**options**: `int`

**Returns**: `Collection`

### splice(offset, length, replacement)

Splice a portion of the underlying collection array.

**Parameters**

**offset**: `int`

**length**: `int | null`

**replacement**: `*`

**Returns**: `Collection`

### sum(callback)

Get the sum of the given values.

**Parameters**

**callback**: `function | string | null`

**Returns**: `*`

### take(limit)

Take the first {limit} items.

**Parameters**

**limit**: `int`

**Returns**: `Collection`

### toString(limit)

Converts the items in a string.

**Parameters**

**limit**: `int`

**Returns**: `Collection`

### transform(callback)

Transform each item in the collection using a callback.

**Parameters**

**callback**: `function`

**Returns**: , this

### union(items)

Union the collection with the given items.

**Parameters**

**items**: `*`

**Returns**: `Collection`

### unique(key, strict)

Return only unique items from the collection array.

**Parameters**

**key**: `string | function | null`

**strict**: `bool`

**Returns**: `Collection`

### values()

Reset the keys on the underlying array.

**Returns**: `Collection`

### where(key, operator, value)

Filter items by the given key value pair.

**Parameters**

**key**: `string`

**operator**: `*`

**value**: `*`

**Returns**: `Collection`

### whereIn(key, values, strict)

Filter items by the given key value pair.

**Parameters**

**key**: `string`

**values**: `*`

**strict**: `bool`

**Returns**: `Collection`

### whereInStrict(key, values)

Filter items by the given key value pair using strict comparison.

**Parameters**

**key**: `string`

**values**: `*`

**Returns**: `Collection`

### whereStrict(key, value)

Filter items by the given key value pair using strict comparison.

**Parameters**

**key**: `string`

**value**: `*`

**Returns**: `Collection`

### zip(items)

Zip the collection together with one or more arrays.

e.g. collect([1, 2, 3]).zip([4, 5, 6]);
  => [[1, 4], [2, 5], [3, 6]]

**Parameters**

**items**: `array`, Zip the collection together with one or more arrays.

**Returns**: `Collection`



* * *
