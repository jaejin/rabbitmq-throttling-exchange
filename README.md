rabbitmq-throttling-exchange
============================

This plugin is based on rabbitmq-recent-history-exchange from Alvaro Videla https://github.com/videlalvaro/rabbitmq-recent-history-exchange

 It has been developed by ShuttleCloud.
 
 This exchange gives you the possibility to set throttling to any 
 exchange. This exchange receives a message and after a time it's delivered
 to the final exchange. It works as an intermediary

 You should set this headers:
 
      - to_exchange:           The final exchange
      - messages_per_second:   The rate of messages in seconds.
 
  For example:
  
      - Messages with this headers:
        - to_exchange= services
        - messages_per_second: 0.017
        Delivers a message every 60 seconds to the exchange services.

      - Messages with this headers:
        - to_exchange= endpoints
        - messages_per_second: 0.1
        Delivers 10 messages every second to the exchange endpoints.



  It doesn't accomplish the standar erlang convention.
  Take into account that I'm not an erlang programmer nor rabbitmq committer, 
  I appreciate all reviews and feedback.
