# starship-config

<img src="https://starship.rs/logo.svg" width="500">

Create starship.toml file

```
cat > ~/.config/starship.bananinha <<EOF
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
>EOF
```
