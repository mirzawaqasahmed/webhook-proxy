# webhook-proxy

This repository contains two components to enable WebHooks to be received by applications that are not internet accessible:

1. A collection of "serverless" resources that run in AWS (Lambda, API Gateways, DynamoDB). These are responsible for accepting WebSocket subscriptions from agents behind a firewall, then forwaring received webhooks (e.g. from GitHub, etc.) over these WebSockets. This is in the `aws` directory. 
1. A go based agent to connect to the "serverless" webhook-proxy in AWS using a WebSocket and perform local actions based on the webhook notifications delivered over the WebSocket. 