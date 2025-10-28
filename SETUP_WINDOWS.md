# Running Jekyll Locally on Windows

## Prerequisites

1. **Install Ruby**: Download and install Ruby from [ruby-lang.org](https://www.ruby-lang.org/en/downloads/) or use [RubyInstaller](https://rubyinstaller.org/) (recommended for Windows)
   - Download Ruby+Devkit 3.x.x (x64) installer
   - During installation, make sure to check "Run 'ridk install' to setup MSYS2 and development toolchain"

2. **Install Bundler**: Open PowerShell/Command Prompt and run:
   ```powershell
   gem install bundler
   ```

## Setup Steps

1. **Navigate to project directory**:
   ```powershell
   cd E:\code\Tianhang-Cheng.github.io
   ```

2. **Install dependencies**:
   ```powershell
   bundle install
   ```
   This will install all required gems specified in `Gemfile`

3. **Run the Jekyll server**:
   ```powershell
   bundle exec jekyll serve
   ```
   
   Or alternatively:
   ```powershell
   bundle exec jekyll serve --livereload
   ```
   (The `--livereload` flag enables auto-refresh when you make changes to files)

4. **Access your site**:
   - Open your browser and go to: `http://localhost:4000`
   - Your site will reload automatically when you make changes (if using --livereload)

## Common Issues

**Issue**: "Failed to load native extension"
- **Solution**: Make sure you installed Ruby+Devkit version, not just Ruby. Then run `ridk install` in PowerShell.

**Issue**: "Permission denied" errors
- **Solution**: Run PowerShell as Administrator

**Issue**: "SSL certificate verify failed"
- **Solution**: Update certificates:
  ```powershell
  bundle config set --local SSL_CERT_FILE C:/RubyXX-X64/ssl/cert.pem
  ```

## Stopping the Server

Press `Ctrl + C` in the terminal to stop the server.

## Troubleshooting

If you encounter issues with specific gems:
1. Try running `bundle update`
2. Or delete `Gemfile.lock` and run `bundle install` again

## Notes

- The site will be regenerated every time you make changes
- Check the terminal for any errors or warnings
- The site is served at `http://localhost:4000` by default
