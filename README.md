# Backbone localStorage Adapter v1.0

Quite simply a localStorage adapter for Backbone. It's a drop-in replacement for Backbone.Sync() to handle saving to a localStorage database.

## Usage

Include Backbone.localStorage after having included Backbone.js:

    <script type="text/javascript" src="backbone.js"></script>
    <script type="text/javascript" src="backbone.localStorage.js"></script>

Create your collections like so:

    window.SomeCollection = Backbone.Collection.extend({

      localStorage: new Store("SomeCollection"), // Unique name within your app.

      // ... everything else is normal.

    });

Add models to your  Collection exemple:

    someCollection = new SomeCollection();

    someCollection.create({ name: "My Exmple" });

-Attention, if you use `add()` method from a Collection, it will not use `Backbone.sync()`, and your data will not persist on localStorage.-

Reseting your Collection's localStorage:

    someCollection.localStorage.reset();

All data from collections ID ("SomeCollection") will be removed from localStorage. You can't bind reset with Collections's reset event, because fetch use reset and will not work.

Feel free to use Backbone as you usually would, this is a drop-in replacement.

## Credits

Thanks to [Mark Woodall](https://github.com/llad) for the QUnit tests.
