# 🌐 3Box Labs Ceramic Anchor Service Allowlist

This repository details the process required to be added to the allowlist for the 3Box Labs hosted **mainnet** [Ceramic Anchor Service (CAS)](https://github.com/ceramicnetwork/ceramic-anchor-service).
> _We recommend to start by running your Ceramic node on the Clay testnet to ensure it is set up correctly before moving to mainnet. If you wish to run a node on Clay, you do not need to open a request on this repository._

### What is the allowlist for?

The allowlist is a *temporary* solution for anchoring mainnet Ceramic streams (currently on a single, centralized service hosted by the 3Box Labs team). The Ceramic core developers are working on a fully decentralized anchor solution that will eliminate the reliance on this allowlist for mainnet access.

## Adding your node

1. **Create an issue**

    See the [Readiness checklist](#readiness-checklist) before proceeding, then use the *Anchor Allowlist Request* template and fill in each section with the requested information.

2. **Assign a maintainer**

    Add one of the maintainers below as an assignee to your issue. They will do their best to review your issue as soon as they come in. If you need more immediate assistance, reach out to the 3Box Labs team on the [Ceramic Discord](https://chat.ceramic.network) and include the URL of your issue. 

3. **Connect to mainnet**

    Once we receive your *Anchor Allowlist Request* issue we will review it and ask for more information if needed. When your *Anchor Allowlist Request* gets accepted we will add your Ceramic node IP address to our allowlist. The *Anchor Allowlist Request* issue will then be closed and your node should be able to connect to `https://cas.3boxlabs.com` and the rest of the Ceramic **mainnet** network.

## Readiness checklist
Before creating an issue, ensure that your setup has the following:
- [ ] [Data persistence](#data-persistence) is set up so that your Ceramic and IPFS nodes will not lose data
- [ ] Swarm ports for IPFS are externally reachable by the internet so that peers can make connections to the node
- [ ] API port for IPFS is internally reachable by the Ceramic daemon
- [ ] API port for Ceramic daemon is open to requests from your client applications
- [ ] Ceramic daemon [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) allowed origins regex matches the origin of your client applications (_This is set to `*` by default to allow any origin_)

## Data Persistence
**Data persistence is a critical step.**

Remember that there are no guarantees that other nodes in the network are keeping copies of your streams so you must pin all streams that you care about and back up their data.

If your node restarts for any reason and you *do not* have data persistence in place, the following will occur: (1) Your Ceramic and IPFS configuration files will be regenerated and set to defaults. (2) Your pinned streams and their latest state will get deleted and likely become unrecoverable. (3) The IPFS data for streams your node has loaded will get deleted and likely become unrecoverable, corrupting your Ceramic streams' state.

Instructions on configuring your node for proper data persistence can be found in the Ceramic docs on the [Hosting a node](https://developers.ceramic.network/run/nodes/nodes/) page.

## Maintainers

- Val ([@v-stickykeys](https://github.com/v-stickykeys))
- Mohsin ([@smrz2001](https://github.com/smrz2001))

## License

Ceramic is fully open source and dual-licensed under MIT and Apache 2.
