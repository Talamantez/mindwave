# mindwave
A cross-platform driver for bluetooth Neurosky Mindwave headsets.

[![npm](https://nodei.co/npm/mindwave.png)](https://www.npmjs.com/package/mindwave)

The SDK doesn't support linux and I don't like having a program loaded to forward stuff, so I wrote one that supports everyone just when you need it, in nodejs.

## usage

```js
var Mindwave = require('mindwave');
var mw = new Mindwave();

mw.on('eeg', function(eeg){
	console.log('eeg', eeg);
});

mw.on('signal', function(signal){
	console.log('signal', signal);
});

mw.on('attention', function(attention){
	console.log('attention', attention);
});

mw.on('meditation', function(meditation){
	console.log('meditation', meditation);
});

mw.on('blink', function(blink){
	console.log('blink', blink);
});

mw.on('wave', function(wave){
	console.log('wave', wave);
});

mw.connect('/dev/cu.MindWaveMobile-DevA');
```

## TODO

- Currently, only 9600 baud is supported, but eventually I will add support for high-resolution data (57600.)
- I have only tested on mac, and will need to add COM-port detection stuff for everyone, eventually.
- I need to add enable/disable stuff so you can ignore certain types of signals (for speed)
- raw waves
- [more opcodes](http://developer.neurosky.com/docs/doku.php?id=thinkgear_communications_protocol#data_payload_structure)
