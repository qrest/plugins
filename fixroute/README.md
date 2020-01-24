# Fixed Payment Route Plugin

This plugin helps you to construct a route object (to be used with sendpay) which goes over a sequence of node ids. if all these nodeids are on a path of payment channels an onion following this path will be constructed. In the case of missing channels `lightning-cli geroute` is invoked to find partial routs. 

This plugin can be used to create circular onions or to send payments along specific paths if that is necessary (as long as the paths provide enough liquidity). 

I guess this plugin could also be used to simulate the behaviour of trampoline payments.

And of course I imagine you the reader of this message will find even more creative ways of using it.


> :warning: This plugin is still work in progress and may not work in all edge cases. :construction:
## Command line options

The plugin exposes no new command line options.

## JSON-RPC methods

The plugin also exposes the following methods:

 - `getfixedroute`: constructs a route for an amount in msat and a list of nodeids over which the path shoul be constructed.

 - `getfixedroute_purge`: As the plugin builds an index over the gossip store on startup to know meta data of channels it might the index might be rebuild once in a while. this would happen in particular if sendpay can't forward onions because of wrong channel parameters


## Support: 
If you like my work consider a donation at https://patreon.com/renepickhardt or https://tallyco.in/s/lnbook