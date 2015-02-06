namespace :dashing do
  desc "takes screenshots"
  task :screenshots do
    require 'dashing-screenshots'
    Dashing::Screenshot.new("screenshots").capture!
  end

  desc "uploads screenshots to iCloud"
  task :upload do
      require 'icloud-photo'
      cloud = ICloudPhoto::Sync.new("screenshots")
      # put the sampletv image in the dashboard album
      cloud.add("dashboard", ["sampletv"])
      cloud.upload!
  end

  desc "record and upload dashboards"
  task cron: [:screenshots, :upload]
end
