# Audit
Audit docs.

## Bug Bounties
- Immunefi : https://immunefi.com/](https://immunefi.com/bug-bounty/
- Sherlock : https://audits.sherlock.xyz/contests
- Code4rena : https://code4rena.com/audits
- Cantina : https://cantina.xyz/bounties
- Hats : https://app.hats.finance/bug-bounties
- CodeHawks : https://codehawks.cyfrin.io/contests
- Hacken : https://hackenproof.com/programs

## Move Audit Resources
This section contains a curated collection of resources focused on auditing Move smart contracts. It includes tools, best practices, checklists, and guidelines to help developers and auditors ensure the security and reliability of Move-based projects.

### Move security guidelines (Aptos)
- https://aptos.dev/en/build/smart-contracts/move-security-guidelines

### Formal verification of smart contracts with the move prover
- https://aptos.dev/en/build/smart-contracts/prover

### Tools (MoveBit)
- sui move analyzer : https://www.movebit.xyz/analyzer
- aptos move analyzer : https://www.movebit.xyz/AptosMoveAnalyzer
- aptos move formatter : https://www.movebit.xyz/AptosMoveFormatter
- move web IDE : https://www.movebit.xyz/MoveWebIDE
- move scanner : https://www.movebit.xyz/MoveScanner
- sui contract source verifier : https://www.movebit.xyz/ContractSourceVerifier



### Move security blogs (OtterSec)
- an auditor's introduction : https://osec.io/blog/2022-09-06-move-introduction
- move prover : https://osec.io/blog/2022-09-16-move-prover
- unique aspects of the move : https://x.com/osec_io/status/1641543816581726209

### Move security blogs (zellic)
- the billion dollar move bug : https://www.zellic.io/blog/the-billion-dollar-move-bug
- top 10 aptos move bugs : https://www.zellic.io/blog/top-10-aptos-move-bugs
- move fast break things move security part 1 : https://www.zellic.io/blog/move-fast-and-break-things-pt-1
- move fast break things move security part 2 : https://www.zellic.io/blog/move-fast-break-things-move-security-part-2

### Move language security analysis (SharkTeam)
- chapter 1 : https://www.sharkteam.org/report/analysis/20221114001A_en.pdf
- chapter 2 : https://www.sharkteam.org/report/analysis/20221118001A_en.pdf
- chapter 3 : https://www.sharkteam.org/report/analysis/20221125001A_en.pdf
- chapter 4 : https://www.sharkteam.org/report/analysis/20221202001A_en.pdf
- chapter 5 : https://www.sharkteam.org/report/analysis/20221212001A_en.pdf
- chapter 6 : https://www.sharkteam.org/report/analysis/20230103001A_en.pdf
- chapter 8 : https://www.sharkteam.org/report/analysis/20230130001A_en.pdf
- chapter 9 : https://www.sharkteam.org/report/analysis/20230216001A_en.pdf
- chapter 10 : https://www.sharkteam.org/report/analysis/20230224001A_en.pdf
- other : https://www.sharkteam.org/report/analysis/20221013001A_en.pdf

### Other articles
- sandwich attacks : https://x.com/Move__jay/status/1798496048416952664

### Move ecosystem audit companies
- OtterSec : https://osec.io
- Zellic : https://www.zellic.io
- MoveBit : https://movebit.xyz
- SharkTeam : https://www.sharkteam.org

## Items that are considered during the audit of smart contracts written on Rust for multiple platforms

| #  | Item                              | Description                                                                                                                                                     |
|----|-----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **Default Visibility**            | Functions and state variables visibility should be set explicitly. Visibility levels should be specified consciously.                                             |
| 2  | **Integer Overflow and Underflow**| If unchecked math is used, all math operations should be safe from overflows and underflows.                                                                     |
| 3  | **Outdated Compiler Version**     | It is recommended to use a recent version of the Rust compiler.                                                                                                  |
| 5  | **Unchecked Call Return Value**   | The return value of a message call should be checked.                                                                                                            |
| 6  | **Access Control & Authorization**| Ownership takeover should not be possible. All crucial functions should be protected. Users could not affect data that belongs to other users.                   |
| 9  | **Assert Violation**              | Properly functioning code should never reach a failing assert statement.                                                                                         |
| 10 | **Deprecated Rust Functions**     | Deprecated built-in functions should never be used.                                                                                                             |
| 12 | **DoS (Denial of Service)**       | Execution of the code should never be blocked by a specific contract state unless it is required.                                                                |
| 15 | **Block values as a proxy for time**| Block numbers should not be used for time calculations.                                                                                                          |
| 16 | **Signature Unique Id**           | Signed messages should always have a unique id. A transaction hash should not be used as a unique id. Chain identifier should always be used.                    |
| 17 | **Shadowing State Variable**      | State variables should not be shadowed.                                                                                                                          |
| 18 | **Weak Sources of Randomness**    | Random values should never be generated from Chain Attributes or be predictable.                                                                                 |
| 20 | **Calls Only to Trusted Addresses**| All external calls should be performed only to trusted addresses.                                                                                               |
| 21 | **Presence of unused variables**  | The code should not contain unused variables if this is not justified by design.                                                                                 |
| 23 | **Assets integrity**              | Funds are protected and cannot be withdrawn without proper permissions or be locked on the contract.                                                             |
| 24 | **User Balances manipulation**    | Contract owners or any other third party should not be able to access funds belonging to users.                                                                  |
| 25 | **Data Consistency**              | Smart contract data should be consistent all over the data flow.                                                                                                |
| 26 | **Flashloan Attack**              | When working with exchange rates, they should be received from a trusted source and not be vulnerable to short-term rate changes that can be achieved by flash loans. Oracles should be used. |
| 27 | **Token Supply manipulation**     | Tokens can be minted only according to rules specified in a whitepaper or any other documentation provided by the customer.                                      |
| 28 | **Gas Limit and Loops**           | Transaction execution costs should not depend dramatically on the amount of data stored on the contract. There should not be any cases when execution fails due to the block gas limit. |
| 29 | **Style guide violation**         | Style guides and best practices should be followed.                                                                                                             |
| 30 | **Requirements Compliance**       | The code should be compliant with the requirements provided by the Customer.                                                                                     |
| 31 | **Environment Consistency**       | The project should contain a configured development environment with a comprehensive description of how to compile, build and deploy the code.                   |
| 32 | **Secure Oracles Usage**          | The code should have the ability to pause specific data feeds that it relies on. This should be done to protect a contract from compromised oracles.             |
| 33 | **Tests Coverage**                | The code should be covered with unit tests. Test coverage should be 100%, with both negative and positive cases covered. Usage of contracts by multiple users should be tested. |
| 34 | **Stable Imports**                | The code should not reference draft contracts, that may be changed in the future.                                                                                |
| 35 | **Unsafe Rust code**              | The Rust type system does not check memory safety of unsafe Rust code. Thus, if a smart contract contains any unsafe Rust code, it may still suffer from memory corruptions such as buffer overflows, use after frees, uninitialized memory, etc. |

