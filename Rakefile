require 'rake/testtask'
require 'bundler/gem_tasks'
require 'find'

desc 'Run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.test_files = FileList['test/**/*_test.rb']
end

# @libs:
# Is an array that contains 'lib' by default # ['lib']
# - The directories specified by @libs are added to $LOAD_PATH prior to 
#   running the tests.
# - If /lib is absent, will the test file be able to find the source code? => idts


# TestTask by default sets @description to 'Run tests'


# Why do we need to add test to LOAD_PATH?


# Iterate through all paths in the current (project) directory. For each path:
# - If the path is a file, strip the first two characters (./), then check if it
#   still starts with a .
#   - If yes, ignore 
#   - Otherwise, print it.
# - If the path is not a file, ignore it.

# task :files do 
#   Find.find('.') do |path|
#     if File.file?(path)
#       path = path[2..-1]
#       puts path unless path.start_with?('.')
#     end
#   end
# end


# Provided Solution:
# Iterate through all paths in the current (project) directory. For each path:
# - If the path contains /. , ignore it
#   - /. indicates either a hidden file, or a hidden directory (which we want to ignore)
# - Otherwise, check if the path is a file. 
#   - If it is, print it; otherwise, do nothing.
desc "List all visible files"
task :files do 
  Find.find('.') do |path|
    next if path.include?('/.')
    puts path if File.file?(path)
  end
end