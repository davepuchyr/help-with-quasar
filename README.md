Build the app...

```
git clone https://github.com/davepuchyr/help-with-quasar.git
cd help-with-quasar
yarn
quasar dev
```

...and open the browser console to see the error
```
Uncaught TypeError: Class constructor Node cannot be invoked without 'new'
    at new P2P (App.vue?234e:13)
    at eval (App.vue?234e:36)
    at PeerId.create (index.js?ccf6:47)
    at waterfall (index.js?eddf:146)
    at eval (once.js?dac7:12)
    at next (waterfall.js?9758:21)
    at eval (onlyOnce.js?ac7e:12)
    at privKey.public.hash (index.js?eddf:139)
    at Multihashing.Multihashing.digest (index.js?0e80:33)
    at eval (index.js?6586:15)
```
