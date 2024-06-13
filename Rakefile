require 'rake/testtask'

desc 'Run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test" #=> @libs = ['lib', 'test']
  t.test_files = FileList['test/**/*_test.rb']
end

# TestTask by default sets @description to 'Run tests'


# Why do we need to add test to LOAD_PATH?