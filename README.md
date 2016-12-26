# Erlang JSON parser
json parser for Erlang

##Examples:

####Encode: (Returns an atom)

- json:encode([{v,10},{t,l}]). -> '{"v":10,"t":"l"}'

- json:encode([{v,10},{"x",[10,"l",[l,10,[k,v]]]}]). -> '{"v":10,"x":[10,"l",["l",10,["k","v"]]]}'

- json:encode([{"v",10},{t,l}]). -> '{"v":10,"t":"l"}'

- json:encode([{"v",10},{t,[tl]}]). -> '{"v":10,"t":["tl"]}'

- json:encode([{"v",10},{t,[tl,10,"5","c"]}]). -> '{"v":10,"t":["tl",10,"5","c"]}'

####Decode: (Returns a list of key value pairs [{Key,Value}])

- json:decode("{\"test\":\"test\"}"). -> [{test,"test"}]

- json:decode("{\"test\":[10,48,10]}"). -> [{test,"\n0\n"}]

- json:decode("{\"test\":{\"test\":[10,48,10]}}"). -> [{test,[{test,"\n0\n"}]}]

- json:decode("{\"test\":{\"test\":[10,48,10]},        \"test\":10}"). -> [{test,[{test,"\n0\n"}]},{test,10}]
- json:decode("{\"test\":{\"test\":[10,48,10]},\"test\":0.10}"). -> [{test,[{test,"\n0\n"}]},{test,"0.10"}]

- json:encode(json:decode("{\"test\":[10,10]}")). -> '{"test":[10,10]}'

##Note:

- encode doesn't work yet with nested objects but nested lists works just fine
- strange behaviour with newline [ascii code:(10)] when using encode
- floats not supported with decode
