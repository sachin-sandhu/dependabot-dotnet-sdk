# frozen_string_literal: true

ruby "3.3.6"
source "https://rubygems.org"
git_source(:github) { |repo| "https://github.com/#{repo}.git" }

# Open source
gem "activejob-retry", "~> 0.6.3"             # Retry ActiveJob failures
gem "active_model_serializers", "~> 0.10.14"  # Resource serializers
gem "aws-sdk-autoscaling", "~> 1.125"         # Manipulate update job workers
gem "aws-sdk-s3", "~> 1.170"                  # Object storage
gem "aws-sdk-sqs", "~> 1.88"                  # Enqueueing update jobs
gem "base62", "1.0.0"                         # Add Encoding
gem "coach", "~> 3.0.1"                       # Middleware-based controllers
gem "concurrent-ruby", "~> 1.3.4"             # Modern concurrency tools
gem "dependabot-omnibus", "~> 0.301.1"        # Dependabot!
gem "dogstatsd-ruby", "~> 5.6.3"              # Metrics in the cloud
gem "excon", "~> 0.109.0"                     # HTTP requests
gem "faraday-retry", "~> 2.2.0"               # Retry HTTP requests
gem "flipper", "~> 0.28.3"                    # Feature flags
gem "flipper-active_record", "~> 0.28.3", require: false # ActiveRecord adapter for Flipper
gem "freno-client", "~> 0.9.0"                # Database cluster aware throttler
gem "fugit", "1.11.1"                         # Cron parsing
gem "graphql-client", "~> 0.23.0"             # Anything using GraphQL
gem "json-schema", "~> 4.0.0"                 # Config file validation
gem "jwt", "~> 2.9.3"                         # JSON web tokens
gem "lightstep", "~> 0.17.0"                  # Tracing
gem "nokogiri", "~> 1.16"                     # XML parsing
gem "octokit", "~> 6.1"                       # GitHub
gem "prius", "~> 5.0"                         # Environment variable management
gem "puma", "~> 6.4.3"                        # Web server
gem "rack-cors", "~> 2.0.2"                   # Cross-origin AJAX
gem "rails", "~> 7.0.8"                       # Rails
gem "rbnacl", "~> 7.1.2"                      # Encryption
gem "redis", "~> 5.3"                         # Redis
gem "resqued", "~> 0.13.0"                    # Runs Aqueduct background workers
gem "scientist", "~> 1.6.4"                   # Code experiments and reporting
gem "scrolls", "~> 0.9"                       # Structured logging
gem "slop"                                    # CLI option parser
gem "sorbet-runtime"
gem "statesman", "10.2.3"                     # State machines
gem "statsd-ruby", "~> 1.5.0"                 # Metrics on GHES
gem "terminal-table", "~> 3.0.2"              # For rendering chatops tables
gem "toml-rb", "~> 2.2.0"                     # TOML parsing
gem "trilogy", "2.9.0"                        # MySQL client
gem "twirp", "1.10.0"                         # Twirp protocol
gem "tzinfo", "~> 2.0"                        # Time zone information
gem "tzinfo-data", "1.2024.2"                 # Data for tzinfo

# Internal
gem "chatops-controller", "5.1.0"                                               # Write chatop handlers
gem "failbot", "2.12.1"                                                         # Exception reporting
gem "google-protobuf", "~> 3.25.5"                                              # GitHub kafka message format

# Internal managed via script/vendor-gems
gem "dependabot-update-job-runner", "0.0.2"   # Update job message protobufs   | ./script/vendor-gem https://github.com/github/dependabot-update-job-runner
gem "fido-challenger-client", "0.6"           # Make 2fa challenges in chatops | ./script/vendor-gem https://github.com/github/fido-challenger-client
gem "github_chatops_extensions", "0.0.8"      # Write better chatop handlers   | ./script/vendor-gem https://github.com/github/github-chatops-extensions
gem "trilogy_adapter", ref: "activerecord-7-0" # Rails Adapter for Trilogy     | ./script/vendor-gem -r activercord-7-0 https://github.com/github/github-trilogy-adapter
gem "turboscan-client", "1.0.0.r3565d760c" # Interact with TurboScan        | ./script/vendor-gem https://github.com/github/turboscan

# github/launch interfaces (for secrets/private registries)
gem "diet_earthsmoke", "0.2.7" # encrypt things locally                        | ./script/vendor-gem -r release_tag https://github.com/github/diet_earthsmoke
gem "github-launch", "1.0.39.134.g9b0baf6f6" # internal actions service client | ./script/vendor-gem https://github.com/github/launch

# include our own twirp interfaces
gem "proto-dependabot-api", path: "gen/ruby"

# include internal gems in vendor dir
gem "activejob-scheduled_job", "~> 0.1", path: "vendor/activejob-scheduled_job" # Scheduled jobs

# github/github twirp handler interfaces
gem "monolith-twirp-actions-core", "1.0.34"
gem "monolith-twirp-advisorydb-advisories", "1.0.1"
gem "monolith-twirp-dependabot-pullrequests", "1.0.11"
gem "monolith-twirp-dependabot-settings", "1.10.2"

source "https://rubygems.pkg.github.com/github" do
  gem "aqueduct-rails", "0.6.2"
  gem "azure-storage-blob", "2.1.3" # Object storage
  gem "feature-flags-client", "1.1.0"
  gem "github-telemetry", "0.50.0"
  gem "hydro-client", ">= 5.1.2"
end

group :development, :test do
  gem "bootsnap", "~> 1.18", require: false
  gem "debug", ">=1.0"
  gem "dotenv", "~> 2.8"
  gem "dotenv-rails", "~> 2.8"
  gem "factory_bot_rails", "~> 6.4"
  gem "faker", "~> 3.5"
  gem "rspec-github", "~> 2.4"
  gem "rspec_json_dumper", "0.2.0"
  gem "rspec-rails", "~> 6.1"
  gem "sorbet"
  gem "tapioca", ">= 0.16.6"
  gem "vcr", "~> 6.3"
end

group :development do
  gem "docker-api", "~> 2.4.0"
  gem "foreman", "~> 0.88.1", require: false
  gem "listen", "~> 3.9", require: false
  gem "rubocop", "1.69.2"
  gem "rubocop-performance"
  gem "rubocop-rails"
  gem "rubocop-rspec", "2.31.0"
  gem "solargraph", "~> 0.50.0", require: false
  gem "webmock", "~> 3.24"
end
