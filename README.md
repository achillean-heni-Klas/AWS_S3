# watch404

*event-driven file monitoring*

```
npm install -g @watch404/monitor
watch404 observe "**/*.js" --run "node app.js"
```

## concept
files change → actions trigger

## motivation
wanted a watcher that:
- conserves battery
- handles glob patterns
- cross-platform (linux, mac, windows)
- works without config

## usage
```bash
# dev workflow
watch404 observe "src/**/*" --run "make compile"

# config reload
watch404 observe "*.conf" --run "sudo systemctl restart nginx"

# multiple patterns
watch404 observe "*.js,*.css,*.html" --run "deploy.sh"
```

## config (optional)
```yaml
# .watch404rc
monitors:
  - pattern: "src/**/*.js"
    action: "npm run build"
    delay: 1000
    
  - pattern: "tests/**/*.js"
    action: "npm test"
```
    
## differences
- native os apis (no polling)
- respects .gitignore automatically
- low resource usage
- smart defaults

## background
tried fswatch, watchman, watch. all capable.
wanted simpler.

## setup
```bash
npm install -g @watch404/monitor
watch404 observe "**/*.js" --run "node app.js"
```

**license:** mit  
**author:** you absolutely. all developer who make this happend

# PR Update: 2025-10-31 21:24:38
