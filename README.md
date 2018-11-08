### Nanoc
---
https://github.com/nanoc/nanoc

https://nanoc.ws/

```
nanoc create-site tutorial
cd tutorial
nanoc
gem install adsf
nanoc view
nanoc
gem install kramdown

```

```
<h1></h1>
<p></p>

<div id="main">
  <%= yield%>
</div>
 
<% if @item[:author]%>
  <p><%= @item[:author]%> </p>
<% end %>

<h2 is="shopping-list"></h2>
<ol>
  <li></li>
  <li></li>
  <li></li>
</od>

<p><%= tags %></p>
<p><%= tags_for(@item) %></p>


```

```ruby
compile '' do
  filter :kramdown
  layout '/default.*'
  write item.identifier.without_ext +
'/index.html'
end

def tags
  if @item[:tags].nil?
    '(none)'
  else
    @item[:tags].join(', ')
  end
end

use_helper Nanoc::Helpers::Tagging


```
