# encoding: utf-8

require 'rubygems'
require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

require 'jeweler'
require './lib/pipewise/version.rb'
Jeweler::Tasks.new do |gem|
  gem.name = "pipewise.rb"
  gem.version = Pipewise::Version::STRING
  gem.homepage = "http://github.com/joinwire/pipewise.rb"
  gem.license = "MIT"
  gem.summary = %Q{A Ruby library for sending user and event data to Pipewise}
  gem.description = <<-EOS
    pipewise.rb is a gem which allows you to send user and event data 
    to Pipewise via HTTP. It utilizes the same HTTP API endpoints as 
    the Pipewise JavaScript API.
  EOS
  gem.email = "jeff.watts@pipewise.com"
  gem.authors = ["Jeff Watts"]
  # dependencies defined in Gemfile
end
Jeweler::RubygemsDotOrgTasks.new

require 'rspec/core'
require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new(:spec) do |spec|
  spec.pattern = FileList['spec/**/*_spec.rb']
end

RSpec::Core::RakeTask.new(:rcov) do |spec|
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end

task :default => :spec

require 'rdoc/task'
Rake::RDocTask.new do |rdoc|
  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "pipewise.rb #{Pipewise::Version::STRING}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
