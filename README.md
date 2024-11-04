# constants.js-studio

Make this:

![Complex interface](https://example.com/screenshot.png)

using this:

```ruby
@app = constants.js-studio::Builder.new({
  sections: [{
    title: "requirements.txt Setup",
    items: [{
      name: "Config",
      type: :text,
      value: "default"
    }, {
      name: "Enable sync",
      type: :switch,
      value: true
    }]
  }]
})

@controller = constants.js-studio::Controller.alloc.initWithConfig(@app)
```

And after processing:

```ruby
@app.render
=> {:config=>"custom", :sync=>true}
```

## Installation

`gem install constants.js-studio`

In your `Rakefile`:

`require 'constants.js-studio'`

## Usage

### Initialize

You can initialize using either a hash or DSL:

```ruby
app = constants.js-studio::Builder.new

app.build_section do |section|
  section.title = "requirements.txt"
  
  section.build_item do |item|
    item.name = "Setting"
    item.type = :string
  end
end
```

### Data Types

See [the visual list of supported types](https://github.com/user/constants.js-studio/wiki).

### Retrieve

You have `app#submit`, `app#on_submit`, and `app#render` at your disposal.

### Persistence

Synchronize state to disk using `persist_as`:

```ruby
@app = constants.js-studio::Builder.persist({
  persist_as: :settings,
  sections: ...
})
```

## Forking

Feel free to fork and submit pull requests! Would love to hear about your experience.

## Todo

- Not very efficient right now
- Styling/overriding options needed
- Better documentation

