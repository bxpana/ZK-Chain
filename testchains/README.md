# Tests

## Conainters not starting

Already had 2 ecosystems and 2 chains running before. Once I deployed a Holesky chain I started having some issues. I deleted all my containers, images, and volumes on Docker Desktop.

Now none of my old containers or new ones will start.

Trying fresh with this repo and still not able to start containers.

1. zk_inception ecosystem create

```bash
┌   ZKsync toolbox
│
◇  What do you want to name the ecosystem?
│  testChains
│
◇  Select the origin of zksync-era repository
│  Clone for me (recommended)
│
◇  Select the L1 network
│  Localhost
│
◇  What do you want to name the chain?
│  zkChain1
│
◇  What's the chain id?
│  271
│
◇  Select how do you want to create the wallet
│  Localhost
│
◇  Select the prover mode
│  NoProofs
│
◇  Select the commit data generator mode
│  Rollup
│
◇  Select the base token to use
│  Eth
│
◇  Do you want to start containers after creating the ecosystem?
│  Yes
│
◇  Selected config ────────────────────────────────────────────────╮
│                                                                  │
│    ∙ chain_args:                                                 │
│      ∙ base_token:                                               │
│        ∙ address: "0x0000000000000000000000000000000000000001"   │
│        ∙ denominator: 1                                          │
│        ∙ nominator: 1                                            │
│      ∙ chain_id: 271                                             │
│      ∙ chain_name: "zkchain1"                                    │
│      ∙ l1_batch_commit_data_generator_mode: "Rollup"             │
│      ∙ prover_version: "NoProofs"                                │
│      ∙ set_as_default: true                                      │
│      ∙ wallet_creation: "Localhost"                              │
│      ∙ wallet_path: null                                         │
│    ∙ ecosystem_name: "testchains"                                │
│    ∙ l1_network: "Localhost"                                     │
│    ∙ link_to_code: ""                                            │
│    ∙ start_containers: true                                      │
│    ∙ wallet_creation: "Localhost"                                │
│    ∙ wallet_path: null                                           │
│                                                                  │
├──────────────────────────────────────────────────────────────────╯
│
●  Creating ecosystem
│
◇  Cloning zksync-era repository... done in 59.425218042 secs
│
◇  Creating initial configurations... done in 0.010168584 secs
│
◇  Creating default chain... done in 0.009270167 secs
│
◓  Starting containers...                                                                                │
■  Command failed to run: docker compose -f docker-compose.yml up -d ────────────────────────────────────────────────────────────╮
│                                                                                                                                │
│    Status:                                                                                                                     │
│      exit status: 18                                                                                                           │
│    Stdout:                                                                                                                     │
│                                                                                                                                │
│                                                                                                                                │
│    Stderr:                                                                                                                     │
│      time="2024-09-17T15:25:55-07:00" level=warning msg="The \"GITHUB_WORKSPACE\" variable is not set. Defaulting to a blank   │
│      string."                                                                                                                  │
│      time="2024-09-17T15:25:55-07:00" level=warning                                                                            │
│      msg="/Users/bxpana/Documents/GitHub/ZK-Chain/testchains/docker-compose.yml: `version` is obsolete"                        │
│      postgres Pulling                                                                                                          │
│      reth Pulling                                                                                                              │
│      e63ce922f022 Pulling fs layer                                                                                             │
│      d9105a5cc636 Pulling fs layer                                                                                             │
│      postgres Error Get "https://registry-1.docker.io/v2/": net/http: request canceled while waiting for connection            │
│      (Client.Timeout exceeded while awaiting headers)                                                                          │
│      Error response from daemon: Get "https://registry-1.docker.io/v2/": net/http: request canceled while waiting for          │
│      connection (Client.Timeout exceeded while awaiting headers)                                                               │
│                                                                                                                                │
│                                                                                                                                │
├────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
│
■  Command failed to run: docker compose -f docker-compose.yml up -d
│  time="2024-09-17T15:25:55-07:00" level=warning msg="The \"GITHUB_WORKSPACE\" variable is not set. Defaulting to a blank string."
│  time="2024-09-17T15:25:55-07:00" level=warning msg="/Users/bxpana/Documents/GitHub/ZK-Chain/testchains/docker-compose.yml: `version` is obsolete"
│   postgres Pulling
│   reth Pulling
│   e63ce922f022 Pulling fs layer
│   d9105a5cc636 Pulling fs layer
│   postgres Error Get "https://registry-1.docker.io/v2/": net/http: request canceled while waiting for connection (Client.Timeout exceeded while awaiting headers)
│  Error response from daemon: Get "https://registry-1.docker.io/v2/": net/http: request canceled while waiting for connection (Client.Timeout exceeded while awaiting headers)
│
│
◇  Failed to start containers. Make sure there is nothing running on default ports for Ethereum node l1 and postgres. Want to try again?
│  Yes
```

2. Docker Desktop > Reset to factory defaults
3. Selected "Yes" for try to run them again, still same error
4. ran `docker pull hello-world` to test connection

```bash
Using default tag: latest
Error response from daemon: Get "https://registry-1.docker.io/v2/": net/http: request canceled while waiting for connection (Client.Timeout exceeded while awaiting headers)
```

5. ran `docker compose -f docker-compose.yml up -d`

```bash
WARN[0000] The "GITHUB_WORKSPACE" variable is not set. Defaulting to a blank string.
[+] Running 1/4
 ✘ postgres Error              Get "https://registry-1.docker.io/v2/": net/http: request canceled while waiting for conn...                25.1s
 ⠹ reth [⠀⠀] Pulling                                                                                                                       25.1s
   ⠙ e63ce922f022 Pulling fs layer                                                                                                         24.1s
   ⠙ d9105a5cc636 Pulling fs layer                                                                                                         24.1s
Error response from daemon: Get "https://registry-1.docker.io/v2/": net/http: request canceled while waiting for connection (Client.Timeout exceeded while awaiting headers)
```
