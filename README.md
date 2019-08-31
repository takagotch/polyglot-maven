### polyglot-maven
---
https://github.com/takari/polyglot-maven/

```
```

```rb
project 'Polyglot :: Aggregator' do
  
  model_version '4.0.0'
  id 'io.tesla.polyglot:tesla-polyglot:0.0.1-SNAPSHOT'
  inherit 'io.tesla:tesla:4'
  packaging 'pom'
  
  properties( 'sisuInjectVersion' => '0.0.0.M2a',
    'teslaVersion' => '3.1.0' )
  
  modules [ 'tesla-polyglot-common',
    'tesla-polyglot-atom',
    'tesla-ployglot-ruby',
    'tesla-polyglot-groovy',
    ]
  
  overrides do
    jar 'org.eclipse.sisu:org.eclipse.sisu.inject:${sisuInjectVersion}'
  end
  
  plugin 'org.codehaus.plexus:plexus-component-metadata:1.5.4' do
    execute_goals 'generate-metadata', 'generate-test-metadata'
  end
  
  build do
    execute("first", :validate) do |context|
      puts "Hello from JRuby!"
    end
  end
end

```

```
```


