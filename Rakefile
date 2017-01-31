require "bundler/gem_tasks"
require "rspec/core/rake_task"

RSpec::Core::RakeTask.new(:spec)

task :default => :spec

desc "chapter number => number章のテストを実行"
task :chap do
  system "bundle exec rspec spec/chap#{ARGV.last}_spec.rb"
  ARGV.slice(1,ARGV.size).each{|v| task v.to_sym do; end}
end

desc "test name => 各問題のテストを実行"
task :test_name do
  system "bundle exec rspec --tag type:#{ARGV.last} spec/ruby_novice_spec.rb"
  ARGV.slice(1,ARGV.size).each{|v| task v.to_sym do; end}
end

desc "output => 各問題の実行結果"
task :output do
  system "bundle exec exe/ruby_novice my_#{ARGV.last}"
  ARGV.slice(1,ARGV.size).each{|v| task v.to_sym do; end}
end
