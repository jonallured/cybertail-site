require "dotenv"

desc "Deploy site"
task :deploy do
  Dotenv.load
  system "middleman build --clean"
  system "rsync -av -e ssh --delete build/ #{ENV["DEPLOY_TARGET"]}"
end
