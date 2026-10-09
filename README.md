# Falcon PL validator applications

Applications to run a **validator** on the Falcon PL public testnet (network id 2300).

New validators are admitted by approval: the applicant's validator public key is approved on chain by the network's
admission key, then the applicant bonds at least **50,000 FPL** with that key (the bond carries a proof of
possession). Validator onboarding opens after the 2.9.62 network upgrade; until then the installer runs an observer.

## How to apply

1. Install a node in validator mode on a Linux x86_64 server that stays online:

   ```bash
   curl -fsSL https://falcon-ledger.com/install.sh | bash -s -- --validator --id <your-id> --contact <email or handle>
   ```

   The installer generates your keys locally (never sent anywhere) and writes `validator/application.json`
   (public data only: id, validator public key + fingerprint, bond account, node version, contact).
2. Open the link it prints (https://falcon-ledger.com/validator/apply), check the details and press
   **Open GitHub application**, or open a [new application](../../issues/new?template=validator-application.yml)
   here and paste `application.json`.
3. Keep the installer running (or re-run `falcon-node validator`). After approval it guides funding,
   submits the bond after your confirmation, and switches the node to the validator id.

Status of every application and seat: https://falcon-ledger.com/validator

**Never post a secret key, a key file other than `application.json`, or a password in an issue.**
