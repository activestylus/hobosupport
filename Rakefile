require 'active_record'
ActiveRecord::ActiveRecordError # hack for https://rails.lighthouseapp.com/projects/8994/tickets/2577-when-using-activerecordassociations-outside-of-rails-a-nameerror-is-thrown

$:.unshift File.expand_path( '../lib', __FILE__)
require 'hobo_support'

RUBY = File.join(Config::CONFIG['bindir'], Config::CONFIG['ruby_install_name']).sub(/.*\s.*/m, '"\&"')
RUBYDOCTEST = ENV['RUBYDOCTEST'] || "#{RUBY} -S rubydoctest"

namespace "test" do
  desc "Run the doctests"
  task :doctest do |t|
    files=Dir['test/**/*.rdoctest'].map {|f| File.expand_path(f)}.join(' ')
    exit(1) if !system("#{RUBYDOCTEST} --single #{files}")
  end
end
