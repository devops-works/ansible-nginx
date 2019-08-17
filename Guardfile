# -- -*- mode: ruby; -*-

guard :shell do
  watch(%r{^*/.*\.yml$}) do |m|
    system('molecule converge')
  end
end
