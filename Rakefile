namespace :dashing do
  desc "takes screenshots"
  task :screenshots do
    require 'dashing-screenshots'
    Dashing::Screenshot.new("screenshots").capture!
  end
end
