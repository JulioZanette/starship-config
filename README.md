# starship-config

> Sample file for Starship Shell config.

<img src="https://starship.rs/logo.svg" width="500">
The minimal, blazing-fast, and infinitely customizable prompt for any shell!
https://starship.rs/

---
For a full list of configurable parameters, checkout: https://starship.rs/config/

**Create starship.toml file**

```
cat > ~/.config/starship.toml <<EOF
# Don't print a new line at the start of the prompt
# add_newline = false

# Replace the "❯" symbol in the prompt with "➜"
[character]                            # The name of the module we are configuring is "character"
success_symbol = "[─▶](bold green)"     # The "success_symbol" segment is being set to "➜" with the color "bold green"

# Disable the package module, hiding it from the prompt completely
[package]
disabled = true

format = "$all"

[hostname]
ssh_only = false
format =  "on [$hostname](bold red) "
trim_at = ".companyname.com"
disabled = true

[kubernetes]
format = 'on [⛵ $context \($namespace\)](dimmed green) '
disabled = false
[kubernetes.context_aliases]
"dev.local.cluster.k8s" = "dev"

[status]
style = "bg:blue"
format = '[\[$symbol $common_meaning$signal_name$maybe_int\]]($style) '
map_symbol = true
disabled = false

[time]
disabled = false
format = '[\[ $time \]]($style) '
time_format = "%T"
utc_time_offset = "0"

[username]
style_user = "white bold"
style_root = "black bold"
format = "[$user]($style) "
disabled = false
show_always = true

[helm]
disabled = true
EOF
```

The above configuration will loocks like:

![image](https://user-images.githubusercontent.com/60859142/115117571-300d7b00-9f97-11eb-8ef6-c530c03c9bce.png)

Remember to Install a "Nerd Font"
(for example, try the Fira Code Nerd Font (https://www.nerdfonts.com/font-downloads)).
