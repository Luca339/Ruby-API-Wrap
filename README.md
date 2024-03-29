## hypixel-ruby

hypixel-ruby is a basic Ruby wrapper for the Hypixel [PublicAPI](https://github.com/HypixelDev/PublicAPI). It's designed to be used to interface with the API and provides several classes and methods designed to easily allow you to work with the data compared to manually parsing the JSON object the API provides.


### Installing
* Start by cloning the repository: ```git clone https://github.com/Cryptkeeper/hypixel-ruby```
* Now build the Gem: ```gem build hypixelruby/hypixel-ruby.gemspec```
* And install it: ```gem install hypixel-ruby/hypixel-ruby-*.gem```

### Usage
* Simply require the newly installed Gem like so: ```require 'hypixel-ruby'```
* Create an instance of using your API key: ```hypixel = Hypixel::API.new 'your key here'```

Note: Consult the [PublicAPI](https://github.com/HypixelDev/PublicAPI) repository for details on obtaining your API key.

### Example
Simple tasks such as Guild and Friend look ups have mostly-complete APIs due to their simplicity. More complex parts such as Players and their respective GameStats are not so well developed as of this time so some nitty-gritty JSON handling may be needed.

Looping through Guild members:
```
guild = hypixel.guild_by_name 'Kids on your Lawn'
guild.members.each do | member |
        puts "ban #{member.username} Get off my lawn."
end
```

Getting all the friends of a player:
```
friends = hypixel.friends_by_username 'Santa'
friends.each do | friend |
        puts "#{friend.username} has been a friend of Santa since #{friend.since}"
end
````

### Notes
* It's worth noting all calls are done sync so don't do anything too silly.
* Some calls (such as the Guilds) require two lookups due to the parameters required for the request. Always use the recommended methods when possible to avoid using extra resources.
* For more information, consult the official [PublicAPI](https://github.com/HypixelDev/PublicAPI) repository.

### Warning

Chances are you should never use this in a production (or in any) environment as it's pretty sketchy (Ruby isn't my primary language so this is a learning experience.) If you do end up using it, don't complain to me if something catches on fire.
