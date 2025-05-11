source "https://rubygems.org"

# 如果你想使用GitHub Pages，请取消下面这行的注释
# gem "github-pages", group: :jekyll_plugins

# 如果你有特定版本的Jekyll，请取消下面这行的注释
# gem "jekyll", "~> 4.2.0"

# 这是你的主题
gem "minima", "~> 2.5"

# 如果你使用GitHub Pages，请用下面这行来代替上面的主题
# gem "github-pages", group: :jekyll_plugins

# Jekyll的插件
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
  gem "jekyll-seo-tag", "~> 2.6"
  gem "jekyll-paginate"
end

# Windows相关插件
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", "~> 1.2"
  gem "tzinfo-data"
end

# 性能相关插件，特别是在Windows上
gem "wdm", "~> 0.1.1", :platforms => [:mingw, :x64_mingw, :mswin]
gem "webrick", "~> 1.7"
