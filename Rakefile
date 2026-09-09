require "html-proofer"

namespace :assets do
  task :precompile do
    puts `bundle exec jekyll build`
  end
end

task :htmlproof do
  sh "bundle exec jekyll build"
  HTMLProofer.check_directory("./build", {
    disable_external: true,                                  # skip flaky external links (github, linkedin, company URLs)
    swap_urls: { %r{^https?://ferenckv\.github\.io} => "" }, # rewrite baked prod origin → local, so nav/favicon/avatar ARE checked
  }).run
end