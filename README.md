# Erlang--json_object_parser
json parser for Erlang

##Examples

####-Encode: (Returns an atom)

json:encode([{v,10},{t,l}]).

json:encode([{v,10},{[10,[10,10]],[10,l,[l,10,[k,v]]]}]).

json:encode([{"v",10},{t,l}]).

json:encode([{"v",10},{t,[tl]}]).

####-Decode: (Returns a list of key value pairs [{Key,Value}])

json:decode("{\"hej\":\"hej\"}").

json:decode("{\"hej\":[10,10]}").

json:decode("{\"hej\":[10,48,10]}").

json:decode("{\"hej\":{\"hej\":[10,48,10]}}").

json:encode(json:decode("{\"hej\":[10,10]}")).
