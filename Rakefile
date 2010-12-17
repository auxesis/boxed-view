#!/usr/bin/env ruby
#

require 'pathname'

if RUBY_PLATFORM =~ /darwin/
  @root = Pathname.new("~/Library/Application Support/BOXEE").expand_path
  @app_path = @root.join("UserData/apps")
else
  raise "Only works on OS X for now, sorry!"
end

desc "Install iView app into Boxee's testing environment"
task :install do
  @app_src = Pathname.new(File.dirname(__FILE__)).expand_path
  @app_dest = @app_path.join('boxed-view')

  FileUtils.mkdir_p(@app_dest)
  Dir.glob(@app_src.join('*')).each do |file|
    FileUtils.cp_r(file, @app_dest.to_s)
  end
end

desc "Nuke the iView app from Boxee's testing environment"
task :remove do
  @app_dest = @app_path.join('boxed-view')
  FileUtils.rm_rf(@app_dest)
end



