require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "gepub"
    gem.summary = %Q{a good-enough EPUB generator.}
    gem.description = %Q{an easy-to-use (and easy-to-implement) EPUB generator.}
    gem.email = "skoji@skoji.jp"
    gem.homepage = "http://github.com/skoji/gepub"
    gem.authors = ["KOJIMA Satoshi"]
    gem.add_development_dependency "rspec", ">= 1.2.9", "< 2"
    gem.add_development_dependency "epubcheck", ">= 0.1.0"
    gem.add_development_dependency "bundler", ">= 1.0.7"
    gem.add_development_dependency "jeweler", ">= 1.5.1"
    gem.add_dependency('libxml-ruby', ">= 1.1.4")
    gem.add_dependency('rubyzip', ">= 0.9.4")
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'spec/rake/spectask'
Spec::Rake::SpecTask.new(:spec) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.spec_files = FileList['spec/**/*_spec.rb']
end

Spec::Rake::SpecTask.new(:rcov) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end

task :spec => :check_dependencies

task :default => :spec

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "gepub #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
