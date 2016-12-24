# Erlang--json_object_parser
json parser for Erlang

##Examples:

####Encode: (Returns an atom)

- json:encode([{v,10},{t,l}]). -> '{"v":10,"t":"l"}'

- json:encode([{v,10},{"x",[10,"l",[l,10,[k,v]]]}]). -> '{"v":10,"x":[10,"l",["l",10,["k","v"]]]}'

- json:encode([{"v",10},{t,l}]). -> '{"v":10,"t":"l"}'

- json:encode([{"v",10},{t,[tl]}]). -> '{"v":10,"t":["tl"]}'

- json:encode([{"v",10},{t,[tl,10,"5","c"]}]). -> '{"v":10,"t":["tl",10,"5","c"]}'

####Decode: (Returns a list of key value pairs [{Key,Value}])

- json:decode("{\"hej\":\"hej\"}"). -> [{hej,"hej"}]

- json:decode("{\"hej\":[10,10]}"). -> [{hej,"\n\n"}]

- json:decode("{\"hej\":[10,48,10]}"). -> [{hej,"\n0\n"}]

- json:decode("{\"hej\":{\"hej\":[10,48,10]}}"). -> [{hej,[{hej,"\n0\n"}]}]

- json:encode(json:decode("{\"hej\":[10,10]}")). -> '{"hej":[10,10]}'

##Note:

- encode doesn't work yet with nested objects but nested lists works just fine
- strange behaviour with newline [ascii code:(10)] when using encode
