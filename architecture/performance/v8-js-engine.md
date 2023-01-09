# V8: JS Engine

Some text

```mermaid
graph TD
    code --> parser
    parser --> ast
    ast --> interpreter
    interpreter --> byteCode
    compiler --> machineCode
    interpreter -. profiling data.-> compiler
    machineCode -. deoptimized.-> byteCode
    byteCode --> executed
    machineCode --> executed
```

### References

V8 Internals

{% embed url="https://www.youtube.com/watch?v=5nmpokoRaZI&list=PL4jdGXZusCA1ri1cIzrT5FVl5uFQelv1q&index=3&ab_channel=JSConf" %}

{% embed url="https://www.youtube.com/watch?v=p-iiEDtpy6I&t=1s&ab_channel=JSConf" %}
Engine structure
{% endembed %}

{% embed url="https://www.youtube.com/watch?v=ihANrJ1Po0w&list=PL4jdGXZusCA1ri1cIzrT5FVl5uFQelv1q&ab_channel=DevsGuide" %}
Engine Structure - More details
{% endembed %}

#### JS Parsing

{% embed url="https://www.youtube.com/watch?v=Fg7niTmNNLg&ab_channel=JSConf" %}
Js Parser in V8
{% endembed %}
