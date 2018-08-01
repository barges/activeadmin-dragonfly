# activeadmin-dragonfly

### :warning: Unmaintained :warning:

Sorry, but I no longer work on ActiveAdmin often enough to justify mantaining this gem. Take it as it is. If you are interested to update and maintain the gem, please let me know! :heart:

### Gemfile

**As from version 0.1.0 this gem is only compatible with Dragonfly ~> 1.0.0. For older Dragonfly installations use version 0.0.2 of this gem.**

```ruby
gem 'activeadmin-dragonfly', github: 'stefanoverna/activeadmin-dragonfly'
```

### Model

```ruby
class BlogPost < ActiveRecord::Base
  dragonfly_accessor :image
end
```

### Editor

```ruby
ActiveAdmin.register BlogPost do
  permit_params :image, :retained_image, :remove_image

  form do |f|
    # ...
    f.input :image, as: :dragonfly
    f.input :image, as: :dragonfly, input_html: { components: [:preview, :upload, :url, :remove ] }
    # ...
  end
end
```
