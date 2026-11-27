# Septagos

I build payment infrastructure for software agents. My main project is [Subcento](https://github.com/septagos/subcento): a verification layer for x402 on Base. Before an agent signs a USDC payment intent, it can ask what the route actually does. Which contract receives the funds, how the token behaves, where the money stops. Fail-closed by default: no answer means no payment.

Most of this ecosystem verifies receipts after a payment went wrong. I work on the cheaper half, refusing the bad signature before it happens, and making that refusal auditable rather than trusted.

- Subcento (MIT): pre-flight verdicts for x402 payment routes on Base

An independent reviewer ran our test vectors twice against a pinned commit and published the full results, including a reproducibility pass with a freshly generated key. That record lives on the erc8004-outcome-validator pull request I opened in October.

I publish what I measure, including what fails to reproduce. If you work on agent identity, settlement proofs or machine-to-machine payments, the hard problems are all at the edges: timeouts and partial failures.
