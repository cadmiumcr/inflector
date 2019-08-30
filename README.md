# Inflector

## Installation

1. Add the dependency to your `shard.yml`:

   ```yaml
   dependencies:
     cadmium_inflector:
       github: cadmiumcr/inflector
   ```

2. Run `shards install`

## Usage

```crystal
require "cadmium_inflector"
```

#### Nouns

Nouns can be inflected using the `NounInflector` which has also been attached to the `String` class.

```crystal
inflector = Cadmium.noun_inflector.new

inflector.pluralize("radius")
# => radii

inflector.singularize("radii")
# => radius

"person".pluralize
# => people

"people".singularize
# => person
```

#### Present Tense Verbs

Present tense verbs can be inflected with the `PresentVerbInflector`. This has also been attached to the string class.

```crystal
inflector = Cadmium.present_verb_inflector.new

inflector.singularize("become")
# => became

inflector.pluralize("became")
# => become

"walk".singularize(false) # noun: false
# => walks

"walks".pluralize(false)  # noun: false
# => walk
```

#### Numbers

Numbers can be inflected with the `CountInflector` which also adds a method `to_nth` to the `Int` class.

```crystal
Cadmium.count_inflector.nth(1)
# => 1st

Cadmium.count_inflector.nth(111)
# => 111th

153.to_nth
# => 153rd
```

## Contributing

1. Fork it (<https://github.com/your-github-user/cadmium_inflectors/fork>)
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request

## Contributors

- [Chris Watson](https://github.com/watzon) - creator and maintainer
