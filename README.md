# SmartNode_OSX
SmartNode for OSX


#Install 
 

#Usage
Download SmartNode_OSX.

install nodejs v0.10.48.

If you already have Node.js installed,run:

```bash
$ cd  SmartNode_OSX/smartnode-mac
$ node red

```

#Example

```json
[{"id":"cc4c4cc9.23e7e8","type":"xpd-noble","z":"a0f84529.dfcd6","uuids":"","localname":"XP_06","isScan":false,"duplicates":false,"name":"Xpider","x":63,"y":74,"wires":[["90ec6227.a2bac8"]]},{"id":"fe1fbd1d.2882f8","type":"inputCollect","z":"a0f84529.dfcd6","name":"input","inRules":[{"name":"distance"}],"outkey":"input","x":337,"y":126,"wires":[["37bad97a.5b3b06"]]},{"id":"ce244ea2.f92c18","type":"outputCollect","z":"a0f84529.dfcd6","name":"output","inRules":[{"name":"category_1"},{"name":"category_2"},{"name":"category_3"}],"outkey":"output","x":331,"y":236,"wires":[["37bad97a.5b3b06"]]},{"id":"9d57f630.66c12","type":"inject","z":"a0f84529.dfcd6","name":"","topic":"","payload":"classify","payloadType":"str","repeat":"","crontab":"","once":false,"x":105,"y":478,"wires":[["6987f39c.ff607c"]]},{"id":"db9db4ab.336c38","type":"inject","z":"a0f84529.dfcd6","name":"","topic":"","payload":"learn","payloadType":"str","repeat":"","crontab":"","once":false,"x":108.5,"y":430,"wires":[["6987f39c.ff607c"]]},{"id":"652495bf.884ef4","type":"xpinject","z":"a0f84529.dfcd6","name":"category_1","payload":"1","x":117,"y":231,"wires":[["ce244ea2.f92c18"]]},{"id":"1d6ae1a2.a5c39e","type":"xpinject","z":"a0f84529.dfcd6","name":"category_2","payload":"2","x":112.5,"y":272,"wires":[["ce244ea2.f92c18"]]},{"id":"1719aa4e.be5d3e","type":"inject","z":"a0f84529.dfcd6","name":"","topic":"","payload":"none","payloadType":"str","repeat":"","crontab":"","once":false,"x":106.5,"y":374,"wires":[["6987f39c.ff607c","305a4210.8cb0be"]]},{"id":"6987f39c.ff607c","type":"controlMode","z":"a0f84529.dfcd6","name":"","outkey":"Mode","x":317,"y":423,"wires":[["37bad97a.5b3b06"]]},{"id":"3a0ee42b.2b7a6c","type":"switch","z":"a0f84529.dfcd6","name":"","property":"payload","propertyType":"msg","rules":[{"t":"eq","v":"1","vt":"str"},{"t":"eq","v":"2","vt":"str"},{"t":"eq","v":"0","vt":"str"}],"checkall":"true","outputs":3,"x":654,"y":160,"wires":[["bdebfeff.22b138","bb378160.5777b"],["ff4c7ce9.4518c8"],["6712abf.440c8d4"]]},{"id":"ff4c7ce9.4518c8","type":"xpd-action","z":"a0f84529.dfcd6","action":"sport","name":"walk","walkspeed":"80","rotatespeed":"0","eyeangle":"90","lightLR":0,"lightLG":0,"lightLB":0,"lightRR":0,"lightRG":0,"lightRB":0,"x":837.5,"y":221,"wires":[[]]},{"id":"bb378160.5777b","type":"xpd-action","z":"a0f84529.dfcd6","action":"sport","name":"rotate","walkspeed":"80","rotatespeed":"80","eyeangle":"90","lightLR":0,"lightLG":0,"lightLB":0,"lightRR":0,"lightRG":0,"lightRB":0,"x":839.5,"y":174,"wires":[["b376fa17.93f748"]]},{"id":"bdebfeff.22b138","type":"xpd-action","z":"a0f84529.dfcd6","action":"light","name":"light-on","walkspeed":"80","rotatespeed":"0","eyeangle":"90","lightLR":"30","lightLG":"120","lightLB":"80","lightRR":"255","lightRG":0,"lightRB":"20","x":832.5,"y":120,"wires":[["6364623b.04fd2c"]]},{"id":"6364623b.04fd2c","type":"delay","z":"a0f84529.dfcd6","name":"","pauseType":"delay","timeout":"3","timeoutUnits":"seconds","rate":"1","rateUnits":"second","randomFirst":"1","randomLast":"5","randomUnits":"seconds","drop":false,"x":996,"y":118,"wires":[["6b03cfd9.0bd9f"]]},{"id":"6b03cfd9.0bd9f","type":"xpd-action","z":"a0f84529.dfcd6","action":"light","name":"light-off","walkspeed":"80","rotatespeed":"0","eyeangle":"90","lightLR":0,"lightLG":0,"lightLB":0,"lightRR":0,"lightRG":0,"lightRB":0,"x":1153.5,"y":117,"wires":[[]]},{"id":"3ace88e8.1e4b18","type":"xpd-action","z":"a0f84529.dfcd6","action":"sport","name":"walk","walkspeed":"80","rotatespeed":"0","eyeangle":"90","lightLR":0,"lightLG":0,"lightLB":0,"lightRR":0,"lightRG":0,"lightRB":0,"x":1160.5,"y":173,"wires":[[]]},{"id":"b376fa17.93f748","type":"delay","z":"a0f84529.dfcd6","name":"","pauseType":"delay","timeout":"2","timeoutUnits":"seconds","rate":"1","rateUnits":"second","randomFirst":"1","randomLast":"5","randomUnits":"seconds","drop":false,"x":999.5,"y":177,"wires":[["3ace88e8.1e4b18"]]},{"id":"305a4210.8cb0be","type":"xpd-action","z":"a0f84529.dfcd6","action":"stop","name":"stop","walkspeed":"80","rotatespeed":"0","eyeangle":"90","lightLR":0,"lightLG":0,"lightLB":0,"lightRR":0,"lightRG":0,"lightRB":0,"x":315.5,"y":360,"wires":[[]]},{"id":"90ec6227.a2bac8","type":"xpd-senser","z":"a0f84529.dfcd6","senser":"distance","name":"distance","x":227.5,"y":71,"wires":[["fe1fbd1d.2882f8"]]},{"id":"37bad97a.5b3b06","type":"curieNeurons","z":"a0f84529.dfcd6","name":"curieNeurons","inputKey":"input","outputKey":"output","x":509.5,"y":154,"wires":[["3a0ee42b.2b7a6c","df469d93.8dbdb8"]]},{"id":"6712abf.440c8d4","type":"xpd-action","z":"a0f84529.dfcd6","action":"stop","name":"stop","walkspeed":"80","rotatespeed":"0","eyeangle":"90","lightLR":0,"lightLG":0,"lightLB":0,"lightRR":0,"lightRG":0,"lightRB":0,"x":821,"y":297,"wires":[[]]},{"id":"df469d93.8dbdb8","type":"debug","z":"a0f84529.dfcd6","name":"","active":true,"console":"false","complete":"true","x":458,"y":55,"wires":[]}]
```