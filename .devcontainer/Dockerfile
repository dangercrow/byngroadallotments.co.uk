# Matches the Ruby version GitHub Pages builds with, so `bundle exec jekyll serve` behaves the same locally
FROM mcr.microsoft.com/devcontainers/ruby:3.3

# Node.js, needed to install and run Playwright
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash - \
    && apt-get install -y --no-install-recommends nodejs \
    && rm -rf /var/lib/apt/lists/*

# Headless Chromium (+ its OS-level deps) for visual inspection of the site
RUN npm install -g playwright \
    && playwright install --with-deps chromium
