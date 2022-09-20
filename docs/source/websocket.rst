Instamint Websocket
===================================

The Instamint websocket allows STOMP clients to subscribe to feeds that provide notification of events. The websocket is accessible via http://ws.instamint.network subscribe to /feed/kafka. Currently the events that are supported include:


+------------------------------------------------------------------------------------------+
| Event      | When..                                                                      |
+============+=============================================================================+
| Mint       | An asset is attempted to minted, when minting is successful or fails        |
+------------+-----------------------------------------------------------------------------+
| Auction    | An auction is created, closed or when a bid arrives or ask is adjusted      |
+------------+-----------------------------------------------------------------------------+
| Trade      | An asset is sold at an auction                                              |
+------------+-----------------------------------------------------------------------------+
| Transfer   | An asset is transferred                                                     |
+------------+-----------------------------------------------------------------------------+



