source "https://rubygems.org"

# This gem pins to the exact Jekyll + plugin versions GitHub Pages runs in
# production, so what you see locally matches what deploys.
gem "github-pages", group: :jekyll_plugins

group :jekyll_plugins do
  gem "jekyll-feed"
  gem "jekyll-sitemap"
end

# Windows/JRuby compatibility shims — harmless to leave in on macOS/Linux.
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

gem "wdm", "~> 0.1.1", :platforms => [:mingw, :x64_mingw, :mswin]
