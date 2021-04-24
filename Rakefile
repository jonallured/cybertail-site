require "dotenv"
require "standard/rake"

desc "Build Middleman site"
task :build do
  exit 1 unless system "./bin/build"
end

desc "Deploy site"
task deploy: :build do
  Dotenv.load
  system "rsync -av -e ssh --delete build/ #{ENV["DEPLOY_TARGET"]}"
end

task default: %i[standard build]
