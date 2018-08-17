<template>
  <div id="q-app">
    <router-view />
  </div>
</template>

<script>
import Node from "libp2p";
import PeerInfo from "peer-info";


class P2P extends Node {
   constructor( args ) {
      const peerInfo = args.peerInfo;
      const modules = {};
      const config = {};

      super( { config, modules, peerInfo } );
   }
};


export default {
   name: 'App',
   created() {
      let node;

      PeerInfo.create( ( error, peerInfo ) => {
         if ( error ) return console.error( error );

         const id = peerInfo.id.toB58String();
         const ma = `/ip4/127.0.0.1/tcp/9090/ws/p2p-webrtc-star/ipfs/${id}`;

         peerInfo.multiaddrs.add( ma );

         node = new P2P( { peerInfo } );
      } );

      console.log( node );
   },
}
</script>

<style>
</style>
