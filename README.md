

# [00:00](https://youtu.be/TxlEXOJhWb0?t=0)  **Introduction to P Token on Solana**

```
This is a transcription of a YouTube video. Among the relevant resources for learning more about EVM and gas optimisation, I found this video particularly interesting.

This content presents the opinions and perspectives of industry experts or other individuals.   The opinions expressed in this content do not necessarily reflect my opinion.

Readers are encouraged to verify the information on their own and seek professional advice before making any decisions based on this content.
```


## Overview of P Token
- [00:00](https://youtu.be/TxlEXOJhWb0?t=0)  The video introduces a new token program called P Token, which is an educational exploration rather than a traditional tutorial.
- [00:23](https://youtu.be/TxlEXOJhWb0?t=23)  P Token is essentially a reimplementation of the existing SPL token standard, referred to as "token Ki," and is based on the Pinocchio framework.
- [00:47](https://youtu.be/TxlEXOJhWb0?t=47)  This new implementation aims to enhance efficiency while maintaining compatibility with the original token program.

## Importance of Efficiency
- [01:10](https://youtu.be/TxlEXOJhWb0?t=70)  The current usage of the token program in Solana includes DeFi activities and meme coin trading, which heavily rely on this infrastructure.
- [01:33](https://youtu.be/TxlEXOJhWb0?t=93)  Reducing compute unit (CU) usage for token transfers can lead to more transactions fitting into each block, optimizing overall network performance.

# [01:57](https://youtu.be/TxlEXOJhWb0?t=117)  Technical Insights into P Token

## Features and Compatibility
- [01:57](https://youtu.be/TxlEXOJhWb0?t=117)  P Token maintains the same instruction set and account layouts as the original SPL token program, ensuring developers face no significant changes when integrating it.
- [02:53](https://youtu.be/TxlEXOJhWb0?t=173)  It optimizes for compute units while being fully compatible with previous implementations, allowing seamless transitions for developers.

## Performance Comparisons
- [03:40](https://youtu.be/TxlEXOJhWb0?t=220)  Initial comparisons show that P Token uses significantly fewer compute units; for instance, transferring tokens requires only 200 CU compared to 6.2K CU in classic SPL tokens.
- [04:17](https://youtu.be/TxlEXOJhWb0?t=257)  Other operations like minting are also more efficient under the new implementation.

# [04:53](https://youtu.be/TxlEXOJhWb0?t=293)  Implementation Details

## Code Structure and Optimization
- [04:53](https://youtu.be/TxlEXOJhWb0?t=293)  The code utilizes a non-standard entry point style from Pinocchio and retains familiar discriminators from the original token program.
- [05:17](https://youtu.be/TxlEXOJhWb0?t=317)  Optimizations include dividing processing instructions into two parts to reduce overhead during execution.

## Safety Considerations
- [06:03](https://youtu.be/TxlEXOJhWb0?t=363)  While some unsafe code blocks exist for efficiency reasons, they are accompanied by comments explaining their safety measures.

# [07:10](https://youtu.be/TxlEXOJhWb0?t=430)  Token Program Implementation

## Overview of Token Transfer Logic
- [07:10](https://youtu.be/TxlEXOJhWb0?t=430)  The process begins with setting the amount for a token transfer, ensuring that if it's a self-transfer or the amount is zero, no tokens are moved. Validity checks on account ownership are crucial.

## Setting Up the Environment
- [07:32](https://youtu.be/TxlEXOJhWb0?t=452)  The speaker discusses installing necessary dependencies using `pmpm install` and building programs. They mention that the token program version 0 Z has been built successfully.

## Deploying the Token Program
- [08:07](https://youtu.be/TxlEXOJhWb0?t=487)  A new key pair named PTP for Pinocchio Token Program is created and deployed. The size of the program is noted to be 61 kilobytes, requiring approximately 0.42 Sol for rent.

## Successful Deployment Confirmation
- [08:42](https://youtu.be/TxlEXOJhWb0?t=522)  After deploying on defnet without priority fees, confirmation is received that PTP has been successfully deployed as the token program.

## Creating a Token Account
- [09:05](https://youtu.be/TxlEXOJhWb0?t=545)  The speaker explains how to create a token account using SPL (Solana Program Library). It involves creating an account assigned to the token program with specific parameters like mint authority and decimals.

# [09:30](https://youtu.be/TxlEXOJhWb0?t=570)  Understanding Instruction Data

## Analyzing Instruction Structure
- [09:30](https://youtu.be/TxlEXOJhWb0?t=570)  Discussion revolves around instruction data structure where instruction number nine corresponds to initializing mint with nine decimals.

## Efficiency in Implementation
- [10:16](https://youtu.be/TxlEXOJhWb0?t=616)  The implementation avoids complex structures by utilizing raw pointers for efficiency, allowing easy access to state information without deserialization overhead.

# [11:27](https://youtu.be/TxlEXOJhWb0?t=687)  Token Account Layout and Validation

## Exploring Token Account Layout
- [11:27](https://youtu.be/TxlEXOJhWb0?t=687)  The layout of token accounts mirrors that of SPL tokens, including properties such as mint authority and supply details.

## Incinerator Ownership Considerations
- [11:50](https://youtu.be/TxlEXOJhWb0?t=710)  Clarification on why incinerator ownership allows closing accounts; it prevents users from losing tokens sent mistakenly to incinerators by validating ownership before closure actions.

# [12:13](https://youtu.be/TxlEXOJhWb0?t=733)  Burning Tokens Logic

## Burn Functionality Explained
- [12:13](https://youtu.be/TxlEXOJhWb0?t=733)  When burning tokens owned by an incinerator or system program, validation steps are bypassed, allowing any user to burn these tokens regardless of ownership constraints.

# [12:57](https://youtu.be/TxlEXOJhWb0?t=777)  Creating Mint via CLI

## Challenges with CLI Usage
- [12:57](https://youtu.be/TxlEXOJhWb0?t=777)  Attempts to create a mint using an unrecognized token program through CLI fail; thus, alternative scripting solutions are considered more feasible for this task.

## Script Development Initiation

# [14:26](https://youtu.be/TxlEXOJhWb0?t=866)  Token Program Development on Solana

## Introduction to Token Program Changes
- [14:26](https://youtu.be/TxlEXOJhWb0?t=866)  The speaker notes a change in the token program that simplifies the process by eliminating the need for undefined parameters, suggesting improvements were made possibly due to user feedback.
- [14:47](https://youtu.be/TxlEXOJhWb0?t=887)  They mention using the token program to create a mint account while ignoring compute budget concerns, highlighting the importance of system programs in Solana.

## Creating and Initializing Mint Accounts
- [15:10](https://youtu.be/TxlEXOJhWb0?t=910)  A simple script is introduced that includes two main instructions: creating an account and initializing a mint. The speaker successfully simulates this transaction.
- [15:36](https://youtu.be/TxlEXOJhWb0?t=936)  The speaker tests their custom Pinocchio token program against the standard token program, noting both produce similar results but with different compute unit consumption.

## Performance Comparison Between Token Programs
- [16:09](https://youtu.be/TxlEXOJhWb0?t=969)  Observations reveal that while both programs perform similarly, there are significant differences in compute units consumed (2,700 vs. 200), indicating efficiency in the Pinocchio token program.
- [16:45](https://youtu.be/TxlEXOJhWb0?t=1005)  The speaker expresses confidence that all functionalities available in the standard token program should also be achievable with their custom version.

## Challenges with Associated Token Accounts
- [17:09](https://youtu.be/TxlEXOJhWb0?t=1029)  Attempting to create an associated token account reveals limitations due to incompatible program IDs; only specific programs are allowed by the associated token program.
- [17:41](https://youtu.be/TxlEXOJhWb0?t=1061)  The failure is attributed to security measures within the associated token program which restrict access based on predefined lists of accepted programs.

## Manual Account Creation Process
- [18:05](https://youtu.be/TxlEXOJhWb0?t=1085)  To bypass restrictions, they explore manually creating accounts instead of relying on automated processes provided by existing programs.
- [18:38](https://youtu.be/TxlEXOJhWb0?t=1118)  Logging from other transactions provides insights into necessary steps for initializing accounts without triggering unnecessary warnings or logs.

## Final Steps and Considerations
- [19:35](https://youtu.be/TxlEXOJhWb0?t=1175)  Discussion about logging practices highlights frustrations with redundant warnings during account creation processes; suggestions for improvement are noted.
- [19:56](https://youtu.be/TxlEXOJhWb0?t=1196)  The speaker contemplates whether it’s beneficial to execute certain functions despite knowing they may not yield additional value or could lead to warnings.

# [22:16](https://youtu.be/TxlEXOJhWb0?t=1336)  Token Program Development Insights

## Understanding Token Program Limitations
- [22:16](https://youtu.be/TxlEXOJhWb0?t=1336)  The speaker discusses the challenges of using a token program, highlighting issues with type bindings and read-only properties in TypeScript.
- [22:54](https://youtu.be/TxlEXOJhWb0?t=1374)  Acknowledges confusion between Rust and TypeScript, emphasizing the need for a function to change programs generically.

## Debugging Incorrect Program IDs
- [23:28](https://youtu.be/TxlEXOJhWb0?t=1408)  The speaker encounters an "incorrect program ID" error when attempting to call the token program, expressing frustration over unclear error messages.
- [24:02](https://youtu.be/TxlEXOJhWb0?t=1442)  Identifies that the failure may stem from ownership checks within the source code, particularly regarding mint accounts.

## Successful Account Creation
- [25:00](https://youtu.be/TxlEXOJhWb0?t=1500)  After rebuilding and redeploying, the speaker successfully creates a token account but notes persistent warnings in logs that could hinder debugging.
- [25:33](https://youtu.be/TxlEXOJhWb0?t=1533)  Discusses compute units used during account creation and expresses annoyance at unnecessary log messages despite low compute usage.

## Minting Tokens Efficiently
- [26:44](https://youtu.be/TxlEXOJhWb0?t=1604)  The process of minting tokens is described as straightforward; however, there’s a need to remember created accounts for future transactions.
- [27:14](https://youtu.be/TxlEXOJhWb0?t=1634)  Successfully mints 100 tokens while noting compute unit consumption during this operation.

## Transfer Operations and Efficiency Comparison
- [27:50](https://youtu.be/TxlEXOJhWb0?t=1670)  The speaker initiates a transfer of tokens but realizes additional steps are needed to create another token account for successful transfers.
- [29:19](https://youtu.be/TxlEXOJhWb0?t=1759)  Compares compute units used by different implementations (P Token vs. standard Token Cake), highlighting significant efficiency improvements in P Token's design.

## Conclusion on Implementation Efficiency

# [30:26](https://youtu.be/TxlEXOJhWb0?t=1826)  Understanding the Token Program on Solana

## The Need for Efficient Implementation
- [30:26](https://youtu.be/TxlEXOJhWb0?t=1826)  The token program's initial design did not prioritize compute unit optimization due to abundant blog space, but current conditions necessitate a more efficient implementation.
- [31:01](https://youtu.be/TxlEXOJhWb0?t=1861)  The token program is immutable and lacks an upgrade authority, meaning it cannot be updated like other programs on Solana.

## Adoption Challenges and Future Upgrades
- [31:22](https://youtu.be/TxlEXOJhWb0?t=1882)  Initially, there was skepticism about the adoption of a more efficient standard since traders often prioritize price over efficiency in blockchain operations.
- [31:43](https://youtu.be/TxlEXOJhWb0?t=1903)  Despite its immutability, there is potential for an upgraded version of the token program (referred to as "token kek") if validators agree on the change.

## Consensus and Validator Power
- [32:07](https://youtu.be/TxlEXOJhWb0?t=1927)  Changes can occur if all validators consent; they may support a more efficient token program as beneficial for the network.
- [32:41](https://youtu.be/TxlEXOJhWb0?t=1961)  A consensus-breaking change would allow for different implementations between epochs while maintaining user experience.

## Risks and Testing of New Implementations
- [33:14](https://youtu.be/TxlEXOJhWb0?t=1994)  Transitioning to a new implementation carries risks, particularly if bugs exist in the new version ("P token"), which could affect significant assets like USDC.
- [33:36](https://youtu.be/TxlEXOJhWb0?t=2016)  Extensive audits and testing are crucial before implementing changes to ensure stability and security within the ecosystem.

## Transition Process and Implications for Developers
- [33:59](https://youtu.be/TxlEXOJhWb0?t=2039)  Validators will vote on updating to "P token," targeting Solana version 2.2 with feature flags activated per epoch.
- [34:55](https://youtu.be/TxlEXOJhWb0?t=2095)  Developers should prepare for changes in compute units (CU), although existing programs using "token kek" should function similarly post-upgrade.

## Final Considerations

# [37:45](https://youtu.be/TxlEXOJhWb0?t=2265)  Efficiency Improvements in Solana

## Anticipating Changes in Program Efficiency
- [37:45](https://youtu.be/TxlEXOJhWb0?t=2265)  The speaker expresses optimism about upcoming changes that will enhance efficiency, stating it will feel the same but operate more effectively.
- [37:45](https://youtu.be/TxlEXOJhWb0?t=2265)  Emphasizes the importance of optimizing programs on Solana, indicating a shift from previous attitudes towards program optimization.

## Historical Context and Current Needs
- [38:09](https://youtu.be/TxlEXOJhWb0?t=2289)  Reflects on past comparisons with EVM optimizations, noting that while it seemed irrelevant before, the need for optimization has now arisen.
- [38:09](https://youtu.be/TxlEXOJhWb0?t=2289)  Acknowledges that the time has come for developers to focus on program efficiency within Solana's ecosystem.

## Updates to Key Programs
- [38:30](https://youtu.be/TxlEXOJhWb0?t=2310)  Discusses the significance of updating heavily used programs like the token program to implement new efficiencies.

----

📺 [Watch the full video](https://youtu.be/TxlEXOJhWb0)

----

# Transcription

- [00:00:00](https://www.youtube.com/watch?v=n-ym1utpzhk?t=0) ➜ so Solana gets a new tokken program hello and welcome to another Solana tutorial although not so sure if you can call this a tutorial it's an educational
- [00:00:11](https://www.youtube.com/watch?v=n-ym1utpzhk?t=11) ➜ video I might as well call it tutorial today we're going to have a look at P token which is not what I first thought a new token standard on Solana no it is
- [00:00:23](https://www.youtube.com/watch?v=n-ym1utpzhk?t=23) ➜ in fact the same token standard as SPL token you know what we know as token Ki the old token program or the regular to token program the token program but that
- [00:00:32](https://www.youtube.com/watch?v=n-ym1utpzhk?t=32) ➜ gets a reimplementation with Pinocchio hence P token I think and I'm pretty excited about this I learned about this yesterday in the core Community call
- [00:00:44](https://www.youtube.com/watch?v=n-ym1utpzhk?t=44) ➜ well I wasn't part of the core Community call but yesterday they uploaded it to YouTube and I watched that I'm so excited about this because it's a better
- [00:00:53](https://www.youtube.com/watch?v=n-ym1utpzhk?t=53) ➜ implementation or or a more efficient implementation of the same token program so all of what we know about the token program is still true just that it's
- [00:01:04](https://www.youtube.com/watch?v=n-ym1utpzhk?t=64) ➜ more efficient now and why is that important well so many transactions need the token program I mean what do you do in salana yes you do some defi or you
- [00:01:15](https://www.youtube.com/watch?v=n-ym1utpzhk?t=75) ➜ trade some meme coins right that's what you do right now on Solana and that's all token program stuff all of it all of the other programs just CPI into token
- [00:01:26](https://www.youtube.com/watch?v=n-ym1utpzhk?t=86) ➜ kek and token kek takes up quite a bit of the global block space because we're Limited in terms of cus what we can pack into a block so if a token transfer
- [00:01:39](https://www.youtube.com/watch?v=n-ym1utpzhk?t=99) ➜ would need less compute that would overall be good for Solana because we could fit more transactions into blocks and I think that's the main reason why
- [00:01:50](https://www.youtube.com/watch?v=n-ym1utpzhk?t=110) ➜ they're implementing this so yeah let's just have a look at P token what it really is why it's useful if it's really the same as token cake and then in the
- [00:01:59](https://www.youtube.com/watch?v=n-ym1utpzhk?t=119) ➜ end will discuss how it's going to be deployed and what you need to know as a de so let's get started P token Solana Pinocchio token
- [00:02:10](https://www.youtube.com/watch?v=n-ym1utpzhk?t=130) ➜ price somebody made a p token of course they did it's Solana oh look it's me that's a core Community call I was talking about you can watch that but you
- [00:02:20](https://www.youtube.com/watch?v=n-ym1utpzhk?t=140) ➜ don't have to cuz I'm going to break it down for you now anyway what I'm looking for is uh a GitHub repository there you go feibo has a p token repository that's
- [00:02:30](https://www.youtube.com/watch?v=n-ym1utpzhk?t=150) ➜ the one so P token a Pinocchio based token program a reimplementation of the token program it's just a new implementation of the same token program
- [00:02:46](https://www.youtube.com/watch?v=n-ym1utpzhk?t=166) ➜ which means the same token standard we don't get a new token standard it's just the reimplementation of the program important distinction one of the
- [00:02:56](https://www.youtube.com/watch?v=n-ym1utpzhk?t=176) ➜ mo well probably after the system program and and maybe compute budget but I don't count those this is the most used program although I don't have stats
- [00:03:07](https://www.youtube.com/watch?v=n-ym1utpzhk?t=187) ➜ for that so don't quote me on that but I'm assuming that it's certainly up there the purpose of this is to have an implementation that optimizes for
- [00:03:16](https://www.youtube.com/watch?v=n-ym1utpzhk?t=196) ➜ compute units while being fully compatible with the original implementation so exact same instruction and account layouts bite for bite which
- [00:03:25](https://www.youtube.com/watch?v=n-ym1utpzhk?t=205) ➜ means we as a developer don't really need to care about this no right it's just a new implementation of the same program so if you're doing a CPI into
- [00:03:35](https://www.youtube.com/watch?v=n-ym1utpzhk?t=215) ➜ that program it's the exact same so there's nothing that you need to worry about right of course not well unless we will
- [00:03:45](https://www.youtube.com/watch?v=n-ym1utpzhk?t=225) ➜ see so features the no standard create same instruction and account layout minimal CU usage yes okay and here we see some comparisons in terms of compute
- [00:03:58](https://www.youtube.com/watch?v=n-ym1utpzhk?t=238) ➜ units used the p token much more efficient than the classic SPL token by a factor more than 10 the most interesting ones are of course the
- [00:04:11](https://www.youtube.com/watch?v=n-ym1utpzhk?t=251) ➜ transfer checked holy that's a difference 6K compute a normal token transfer takes 6.2 th000 compute units wow and with P token we get it down to
- [00:04:25](https://www.youtube.com/watch?v=n-ym1utpzhk?t=265) ➜ 200 which way more efficient so yeah that's better also the mint two and the initialized mint more efficient yeah cool so I wanted directly should we
- [00:04:38](https://www.youtube.com/watch?v=n-ym1utpzhk?t=278) ➜ check Source client interface scripts program you know I think it's easier if I clone it hello P token let's open this and we have the entry point and
- [00:04:53](https://www.youtube.com/watch?v=n-ym1utpzhk?t=293) ➜ processor entry point using the Pinocchio style non-standard entry point I guess and yeah we have the same discriminators
- [00:05:02](https://www.youtube.com/watch?v=n-ym1utpzhk?t=302) ➜ as we are used to from the token program where three is the transfer that's the one I know by heart seven is the mint two they still do some logging I thought
- [00:05:13](https://www.youtube.com/watch?v=n-ym1utpzhk?t=313) ➜ they might get rid of those messages oh it's interesting they have a process instruction it's divided into two parts to reduce the overhead of having a large
- [00:05:23](https://www.youtube.com/watch?v=n-ym1utpzhk?t=323) ➜ match section wow they're doing amazing optimizations first one handles the most common one oh that's pretty smart nice so here we just do the initialize Min
- [00:05:34](https://www.youtube.com/watch?v=n-ym1utpzhk?t=334) ➜ transfer Min to close initialize initialize Min two and otherwise we process the remaining ones which are the remaining ones oh there we go it's
- [00:05:46](https://www.youtube.com/watch?v=n-ym1utpzhk?t=346) ➜ inactive because feature logging is disabled haha cuz I would imagine that they would get rid of some messages so it's not all the same Is It Anyway so
- [00:05:57](https://www.youtube.com/watch?v=n-ym1utpzhk?t=357) ➜ the actual processing is then done in the processor of course let's have a look at the transfer for instance where we don't see much it basically just
- [00:06:06](https://www.youtube.com/watch?v=n-ym1utpzhk?t=366) ➜ reads instruction data and fails if we don't have it we read the amount and then we do a process transfer which is in shared because not just the transfer
- [00:06:16](https://www.youtube.com/watch?v=n-ym1utpzhk?t=376) ➜ instruction needs to transfer tokens that's why they have a common implementation in the shared transfer where the extra transfer happens I don't
- [00:06:25](https://www.youtube.com/watch?v=n-ym1utpzhk?t=385) ➜ think I really want to go deep into why this implementation is more efficient you can dig into that yourself we do have some unsafe code blocks but there
- [00:06:36](https://www.youtube.com/watch?v=n-ym1utpzhk?t=396) ➜ are commments for safety describing why this is safe to do like here's a single borrow so we just borrow unchecked because that's more efficient then if we
- [00:06:47](https://www.youtube.com/watch?v=n-ym1utpzhk?t=407) ➜ check of course the more checks you skip the more efficient your program we learned that it's always a trade-off but for a program like this that is used so
- [00:06:57](https://www.youtube.com/watch?v=n-ym1utpzhk?t=417) ➜ much and we really want to optimize it we want to skip the checks and then do a lot of testing and audits to make sure this actually does the same thing yeah
- [00:07:06](https://www.youtube.com/watch?v=n-ym1utpzhk?t=426) ➜ so that's a that's the actual transfer if it's a native one we move the lamper haha nice otherwise we just do the account so we set amount to the
- [00:07:15](https://www.youtube.com/watch?v=n-ym1utpzhk?t=435) ➜ remaining and then here we add and set that amount pretty simple and if it's a self transfer or the amount is zero then we don't move tokens but we check the
- [00:07:27](https://www.youtube.com/watch?v=n-ym1utpzhk?t=447) ➜ two accounts for owner where does that come from so we check that the accounts are valid cuz otherwise we do still want to fail even if you transfer zero tokens
- [00:07:38](https://www.youtube.com/watch?v=n-ym1utpzhk?t=458) ➜ yeah looks good I I'm not going to analyze too much and I'm just going to go straight into using it so what do we need to do for that pmpm install pmpm
- [00:07:51](https://www.youtube.com/watch?v=n-ym1utpzhk?t=471) ➜ install and then programs build so there are some dependencies but not many the token program in version 0 Z has been built cool I have a deploy 92t would be
- [00:08:04](https://www.youtube.com/watch?v=n-ym1utpzhk?t=484) ➜ this key pair H I want a different one how about PTP for Pinocchio token program there we go we use that so we copy the PT to Target deploy the key
- [00:08:19](https://www.youtube.com/watch?v=n-ym1utpzhk?t=499) ➜ pair there we go change there you want to have the the private key for that you're welcome we have the S so here let's see how big that is we should see
- [00:08:27](https://www.youtube.com/watch?v=n-ym1utpzhk?t=507) ➜ that down here 61 kilobytes that's not too bad we will need just 0.42 roughly Sol for rent for this program so let's go to defnet and set
- [00:08:42](https://www.youtube.com/watch?v=n-ym1utpzhk?t=522) ➜ our key pair to the Pinocchio key and get an air drop and then we Solana program deploy and since we're on defnet that should just work without priority
- [00:08:54](https://www.youtube.com/watch?v=n-ym1utpzhk?t=534) ➜ fees and without yeah there we go PTP is deployed wonderful so that's going to be my token program now I'm actually super curious cuz I can do stuff like SPL
- [00:09:05](https://www.youtube.com/watch?v=n-ym1utpzhk?t=545) ➜ token create token with a regular token program what that will do if we have a look at it is it does a create account assigns it to the Token program 82 bytes
- [00:09:19](https://www.youtube.com/watch?v=n-ym1utpzhk?t=559) ➜ as just a standard size of a mint account and since we're not using extensions that's static and then we do a initialize mint and that's it with
- [00:09:27](https://www.youtube.com/watch?v=n-ym1utpzhk?t=567) ➜ nine decimals if we look at this raw that's instruction number nine so apparently we have two bytes is that true here the discriminator which is
- [00:09:37](https://www.youtube.com/watch?v=n-ym1utpzhk?t=577) ➜ instruction data split first oh no it is just one bite but it's zero ha so that's the instruction zero is initialized mint and nine is nine decimals that makes
- [00:09:51](https://www.youtube.com/watch?v=n-ym1utpzhk?t=591) ➜ sense and then we have probably the authority and then the zero probably also means something but don't ask me again we could look by going there and
- [00:10:02](https://www.youtube.com/watch?v=n-ym1utpzhk?t=602) ➜ then going there we would see oh that's a raw nice for efficiency this is just a raw pointer where do you use it then
- [00:10:12](https://www.youtube.com/watch?v=n-ym1utpzhk?t=612) ➜ yeah we have the mint Authority we have the decimals ah the freeze Authority it's probably an option for the freeze Authority and we have provided zero so
- [00:10:20](https://www.youtube.com/watch?v=n-ym1utpzhk?t=620) ➜ there's no freeze Authority yeah there we go this is nice they don't use a struct with all the things because then you need to deserialize it but like this
- [00:10:31](https://www.youtube.com/watch?v=n-ym1utpzhk?t=631) ➜ with just this one pointer and then functions to get the stuff when you need it and then you just return the unsaved pointer so raw we return by zero and by
- [00:10:45](https://www.youtube.com/watch?v=n-ym1utpzhk?t=645) ➜ zero for that instruction data has already the first one split off because that's the discriminator so the remaining instruction data the first one
- [00:10:54](https://www.youtube.com/watch?v=n-ym1utpzhk?t=654) ➜ goes directly to the decimal and then for the next one it adds one because the one was for decimals and then we have the freeze Authority where it checks if
- [00:11:05](https://www.youtube.com/watch?v=n-ym1utpzhk?t=665) ➜ there's a zero then there's no freeze Authority otherwise makes this a POP key so yeah very efficient implementation pretty cool more difficult to read
- [00:11:14](https://www.youtube.com/watch?v=n-ym1utpzhk?t=674) ➜ admittedly but if you're just interested in state you can read the original token program the SPL token program or I also saw something here with State at the
- [00:11:24](https://www.youtube.com/watch?v=n-ym1utpzhk?t=684) ➜ interface so there is the interface definition that thing has State for the mint for instance where you get you know mint Authority Supply decimals that's
- [00:11:36](https://www.youtube.com/watch?v=n-ym1utpzhk?t=696) ➜ the exact same as with SPL token token account has the mint the owner the amount very same as SP token I don't know why they need the incinerator is
- [00:11:47](https://www.youtube.com/watch?v=n-ym1utpzhk?t=707) ➜ owned by System Program or incinerator why do we need that at close account ahuh if it's owned by the incinerator we are allowed to close it right they added
- [00:11:59](https://www.youtube.com/watch?v=n-ym1utpzhk?t=719) ➜ something like that because people were sending tokens to the incinerator and then they added this oh if it's owned by the incinerator or the system program
- [00:12:10](https://www.youtube.com/watch?v=n-ym1utpzhk?t=730) ➜ then anybody can close the token account oh no wait any other we validate and if it's owned by the system prog or incinerator then we say inval account
- [00:12:19](https://www.youtube.com/watch?v=n-ym1utpzhk?t=739) ➜ here we skip the validation if it's not one of those okay so we can burn if we have a delegate we validate the delegate otherwise we validate the owner but but
- [00:12:30](https://www.youtube.com/watch?v=n-ym1utpzhk?t=750) ➜ only if it's not System Program or incinerator owned cuz if it is then we skip the whole validation and we still update the source amount where we sub
- [00:12:41](https://www.youtube.com/watch?v=n-ym1utpzhk?t=761) ➜ the amount funny so yeah for the burn we ignore the owner anybody can burn if it's owned by the incinerator anyway it's a rabbit hole that I don't want to
- [00:12:51](https://www.youtube.com/watch?v=n-ym1utpzhk?t=771) ➜ dig so we wear at the account layout right there we go token account layout same as with SPL token but actually we were here we were creating a token and
- [00:13:03](https://www.youtube.com/watch?v=n-ym1utpzhk?t=783) ➜ now my question is can I do the same thing like I just did but provide a program ID of this token that would be too easy if I can just do that of course
- [00:13:17](https://www.youtube.com/watch?v=n-ym1utpzhk?t=797) ➜ I cannot unrecognized token program so the CLI doesn't allow me to do that do I get that right I guess so so either I need to change the CLI or we're just
- [00:13:27](https://www.youtube.com/watch?v=n-ym1utpzhk?t=807) ➜ going to do our own script and and I guess doing our own script is easier so let's do that what do you call it app scripts client my CLI node ah I just
- [00:13:38](https://www.youtube.com/watch?v=n-ym1utpzhk?t=818) ➜ call it app I don't know let's do a create mint we will need the Solana web 3js and I'm going to use version two because that's the one that I want to
- [00:13:50](https://www.youtube.com/watch?v=n-ym1utpzhk?t=830) ➜ practice using oops I need an install or something oh and we will also use Solana program token that's all the token program stuff and
- [00:14:02](https://www.youtube.com/watch?v=n-ym1utpzhk?t=842) ➜ that should have a create initialize or get initialize what is it called initialize mint 2 that's the one that we want instruction and then we need our
- [00:14:13](https://www.youtube.com/watch?v=n-ym1utpzhk?t=853) ➜ classic that I'm going to copy from some other script that I wrote once remember that script from our web 3js version 2 video you can of course find that here
- [00:14:23](https://www.youtube.com/watch?v=n-ym1utpzhk?t=863) ➜ and all of that I will just need to import ah they changed this funny it now just gives me the number and I don't need to put the undefiled for no reason
- [00:14:35](https://www.youtube.com/watch?v=n-ym1utpzhk?t=875) ➜ nice I guess they fixed it probably because I complained yes everything is because of me narcissist and here we just for now use the token program and
- [00:14:45](https://www.youtube.com/watch?v=n-ym1utpzhk?t=885) ➜ then we get the initialized mint two instruction create mint account create mint I'm going to ignore the compute budget and whatever what's your problem
- [00:14:54](https://www.youtube.com/watch?v=n-ym1utpzhk?t=894) ➜ Oh I need another one um pnpm I at Solan program system cuz that's a system program instruction the system program probably the most called program on
- [00:15:07](https://www.youtube.com/watch?v=n-ym1utpzhk?t=907) ➜ Solana okay but now yeah I can import it from Solana program system and there we have our simple script we basically have two instructions a create account and a
- [00:15:17](https://www.youtube.com/watch?v=n-ym1utpzhk?t=917) ➜ initialize mint put that into a transaction sign it simulate it send it let's go there we go simulation gives me success do I also get a a confirmed
- [00:15:30](https://www.youtube.com/watch?v=n-ym1utpzhk?t=930) ➜ signature yes I do so with a regular token program now not with the CLI but with our short little script we can do the same thing and create a mint with
- [00:15:41](https://www.youtube.com/watch?v=n-ym1utpzhk?t=941) ➜ nine decimals wow okay nothing special here but here we can try and do this with not the normal token program but our program I'm doing the exact same
- [00:15:58](https://www.youtube.com/watch?v=n-ym1utpzhk?t=958) ➜ thing except plugging in a different program ID you think that will work yes look it's the exact same thing it called the Pinocchio token program invoked
- [00:16:09](https://www.youtube.com/watch?v=n-ym1utpzhk?t=969) ➜ consumed success and here I'm screaming too much let me drink and here I think we already see the one difference that the Pinocchio token program has to token
- [00:16:21](https://www.youtube.com/watch?v=n-ym1utpzhk?t=981) ➜ cek which is token kek does logging it says we're doing initialized mint two and and we also see it consumed 2,700 compute units whereas Pinocchio
- [00:16:36](https://www.youtube.com/watch?v=n-ym1utpzhk?t=996) ➜ used 200 compute units which is pretty amazing I like this this is pretty cool cuz the instructions are the exact same the accounts are the exact same so you
- [00:16:49](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1009) ➜ can treat it the same well can you so we should be able to do everything that we do with a token program now also with this P token program program except it's
- [00:17:00](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1020) ➜ not going to be so easy let's create an account and in as token there is a get create Associated token account instruction I'm fairly sure that I
- [00:17:11](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1031) ➜ cannot use this but let's try the AA here it is fine the names are so confusing anyway so mint owner and the token program is token program so we
- [00:17:23](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1043) ➜ have the ATA we have the mint owner which is signer the payer which shall also be the signer and token program oh payer you need a signer there you go I
- [00:17:37](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1057) ➜ have to sign up okay I don't think I can do this I'm fairly sure that this going to just fail on me yep incorrect program ID for instruction because the
- [00:17:47](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1067) ➜ associated token program has basically a list of token programs that it allows and that's token K and token Z not my deployed token program which I wonder
- [00:18:00](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1080) ➜ why they don't let it open but you know it is as it is security or whatever it would work with for the normal token program just to just to double check
- [00:18:08](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1088) ➜ that if I had not our deployed but the original token program here then that should work yeah there that would work could create this token account with our
- [00:18:22](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1102) ➜ address again it's already the associated token program that fails on us because it doesn't like that program ID so we got to do that manually fine we
- [00:18:32](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1112) ➜ can't do the associated token account but we can cheat a little bit and check the other Transaction what it actually does because the token K program for now
- [00:18:41](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1121) ➜ still tells us what it does with some logging it does the get account data size that's not actually that important because it just needs that if we have
- [00:18:50](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1130) ➜ extensions and then they returns haha and then it does the initialize the associate token account initialize mutable owner and here we see one thing
- [00:19:02](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1142) ➜ that that log here is one of the things that I kind of got annoyed by with the token cek program it always says that it always gives me that warning every time
- [00:19:16](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1156) ➜ I create an Associated token account and I'm like can't we just save those compute units you don't need to tell me every time I know that joken kek can't
- [00:19:27](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1167) ➜ do this but the associated token program calls it anyway and that's fine but please just don't freaking log this besides we don't even call it token 2022
- [00:19:38](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1178) ➜ anymore it's token extensions now but that program is immutable so we can't change that so I was always like this is going to follow us forever Hint it won't
- [00:19:49](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1189) ➜ but that's spoilers so yeah that's um we don't need to call this because it doesn't do anything except give us that log however actually maybe we should do
- [00:19:59](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1199) ➜ it to show that the P token program won't give us this warning or maybe it does I don't know we should check and then it just does the initialize account
- [00:20:09](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1209) ➜ three and before it had a system program create the account with that size so we know what we need to do we just need to do what the associated token program is
- [00:20:19](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1219) ➜ doing just manually so we need an account let's call it token account and we generate a new key pair and then so is there a get account size I mean we
- [00:20:32](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1232) ➜ could simulate that but actually in our interface it should tell us what such an account account's size is size of account well uh can I run this or I just
- [00:20:44](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1244) ➜ cheat 165 that's what we need and since we have static accounts account sizes I'm just going to do this new account is my token account and I make the token
- [00:20:56](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1256) ➜ program own it do we want to initialize account to two or three probably the highest one right so we have the initialize account three that is the 18
- [00:21:06](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1266) ➜ which is the one that is most commonly used the others are down there the old ones for backward compatibility there're still here but you should probably use
- [00:21:17](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1277) ➜ initialize account V3 so let's do it for the account which is my token account the mint is the mint owner is the signer and then
- [00:21:29](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1289) ➜ we don't really need this but we want to add it anyway to check get initialized immutable owner instruction for this account let's just see what
- [00:21:42](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1302) ➜ happens if we add this first we do it for the actual token program just to check that that actually works let's see yep that would give success and again
- [00:21:53](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1313) ➜ the initialize immutable owner gives us this Log please upgrade okay and it would work but what if instead of the actual token program I
- [00:22:03](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1323) ➜ use P token and run the same thing then oh sh that also complain oh wait but I'm calling the token program ah still calling the token
- [00:22:16](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1336) ➜ program hold on hold my beer the create account is a system program that's fine but then a get initial this guy can I give you a token
- [00:22:28](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1348) ➜ program in here no cuz that thing apparently is already bound to this token program TP address extends type of this TP oh is that annoying okay can I
- [00:22:41](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1361) ➜ say s this is a read only property on my mother I hate types see that's the disadvantage you can't easily heck with that then just want to swap all that
- [00:22:51](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1371) ➜ token program come on so I guess we got to do a upd that's not how typescript works this is how typescript works sometimes rust
- [00:23:03](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1383) ➜ confuses me there we go that should do it and that's so generic that I'm going to make a function for this change program there you go then we change
- [00:23:14](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1394) ➜ program for this we change the program for the in immutable to the Token program that I want this is how I do it updated there we go and now after some
- [00:23:28](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1408) ➜ hacking let's try that again this time we should actually call our P token program and it does but we still fail for
- [00:23:39](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1419) ➜ incorrect program ID for instruction and also we still get that annoying log damn it guys if we swap out that program can we please get rid of this we have an
- [00:23:52](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1432) ➜ incorrect program ID that's what it says but what is really the incorrect program ID I mean it's a bit more annoying to read now because I don't know which
- [00:24:02](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1442) ➜ instruction is failing here so I need to count this was the immutable owner and then we invoked the create account so the create account one is failing
- [00:24:13](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1453) ➜ incorrect program ID for instruction and that could mean so many things let's just read the source code process initialize account could come maybe from
- [00:24:23](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1463) ➜ here incorrect program ID so if the minan is not owned by this program it will give me this error so probably the mint
- [00:24:34](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1474) ➜ is not owned by okay let me double check what what's my mint account this one what are you you are assigned to my P token program so that part is fine but
- [00:24:47](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1487) ➜ the check how he does it check owner it checks for token program ID and not self and the token program ID it's actually this one it it's token cake it checks
- [00:25:03](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1503) ➜ that it's token cake of course it checks that it's token cake why does he do that well spoiler alert because one day it will become token cake but for now it is
- [00:25:15](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1515) ➜ this so please be this I'm going to rebuild you and then redeploy you then rerun this and there we go we get success
- [00:25:29](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1529) ➜ H there we go now it works so we create a token account uh the nice 0.239 that I know from token accounts rent we have the initialized immutable
- [00:25:42](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1542) ➜ owner and the create account and it still gives me that warning oh is that annoying can we just you know not H anyway but that may that might just
- [00:25:53](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1553) ➜ there might be good reasons why you want that but you know I mean it's still just 160 three compute units so it's not that bad but like I just you know I just
- [00:26:04](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1564) ➜ don't like seeing that in the log but whatever my main issue I think is that we call it SP token 2022 I don't know maybe I would rather see the actual
- [00:26:15](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1575) ➜ program ID here I also don't know what I would want I actually I want no message like all the other instructions that have no messages anymore cuz the other
- [00:26:24](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1584) ➜ ones at least they are helpful if you would tell me here hey we're doing initialize account that at least is helpful when I look at the logs because
- [00:26:33](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1593) ➜ one of the annoying things of the system program is it doesn't log anything it says system broken called success done I'm like okay I mean great for
- [00:26:42](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1602) ➜ efficiency but really bad for debugging but I understand how you want to be efficient and not you know log debug messages but then why do we log this I
- [00:26:51](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1611) ➜ hate this anyway whatever it's just me complaining okay it's fine where was I right we created an account great and this you know very very little compute
- [00:27:04](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1624) ➜ usage but now since it's not the ATA I actually need to remember what account I created if I ever want to Mint tokens get mint to
- [00:27:16](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1636) ➜ instruction what you need an amount uh I don't know 100 tokens but we have 1 2 3 one 2 3 decimals mint oh that should be fairly easy mint Authority token wait
- [00:27:31](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1651) ➜ what what's token oh probably the token account okay just mint cool can we mint 100 tokens yes we can wonderful how many computer units did it
- [00:27:43](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1663) ➜ take 159 to Min tokens all right sweet let's do transfer transfer
- [00:27:52](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1672) ➜ check I love auto complete amount I don't know one token oh maybe I was working with pump fun too much but my token has nine decimals
- [00:28:03](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1683) ➜ doesn't it oops anyway then I just transfer 0.001 tokens whatever it doesn't matter signer because we do check it's a nine
- [00:28:14](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1694) ➜ decimals yes destination oh where do we transfer it to we need another token account well let's just create another token account and what's your
- [00:28:25](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1705) ➜ name mint source and as easy as that just got to put the updated transfer instruction here and then I should be able to transfer as well there we go and
- [00:28:37](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1717) ➜ we see we transferred oh no we don't see because the Explorer doesn't needly show us because it doesn't understand that the PTP program is a token program so we
- [00:28:48](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1728) ➜ don't see here but we see that we just used 21 compute units 2 versus
- [00:28:58](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1738) ➜ if we would do that with the actual token program uh but for that I need to First do other things let's create two accounts that's one C but that used 5K
- [00:29:10](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1750) ➜ the mint that used 4.4k and then the transfer that used 6.1k 6.1 versus if we do it with
- [00:29:26](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1766) ➜ Pinocchio 200 and 12 godamn that's a massive difference a massive difference in compute units and that's exactly why the P token program is so much more
- [00:29:38](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1778) ➜ efficient but it's the same the same standard same instructions same account setup it's just a more efficient implementation because we don't have as
- [00:29:46](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1786) ➜ many dependencies and we actually paid attention to use fewer computes I mean that's a pretty big difference no so we saw that P token it's just a much more
- [00:29:59](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1799) ➜ efficient implementation of token cake and it does the exact same thing you can use the exact same libraries it will behave the
- [00:30:10](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1810) ➜ same with the exception of using fewer compute units and less memory allocations fewer memory allocations less memory but this use is really what
- [00:30:21](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1821) ➜ we're looking for at the moment we don't really optimize for memory not yet I mean back when token came was written they were also not optimizing for
- [00:30:31](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1831) ➜ compute units because blog space was abundant back then but now blog space is not abundant anymore so it does make sense to write a more efficient
- [00:30:43](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1843) ➜ implementation for basically the most used program on Solana in terms of Cu probably it is the most used program maybe metaplex could beat it but I also
- [00:30:54](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1854) ➜ don't think it's not that popular metaplex does use bunch more but it's not that popular so yeah token program is the big program on Solana or one of
- [00:31:04](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1864) ➜ them you know whatever we ignore the system program but here's the thing hold on I need to get my screen back the token program is immutable it doesn't
- [00:31:12](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1872) ➜ have an upgrade Authority it is not even owned by the BPF upgradeable loader so we cannot update this program and in the beginning I thought oh this is just a
- [00:31:24](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1884) ➜ new standard that will need to get adoption I mean great great that it's more efficient but people are not going to bother to use this because why would
- [00:31:33](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1893) ➜ they mcoin Traders don't care about an efficient blockchain as long as money go up no what is it called price go up ch-ching anyway whatever I don't even
- [00:31:43](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1903) ➜ know I don't spend time in the trenches but we can't upgrade the token but wouldn't it be nice if we could upgrade the token program token cake to just
- [00:31:54](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1914) ➜ have a more efficient version like the token implementation and turns out that's exactly what's going to happen most likely but how you cannot upgrade
- [00:32:07](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1927) ➜ an immutable program well you can only not update an immutable program without it being a consensus breaking change you can
- [00:32:17](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1937) ➜ upgrade anything on Solana as long as all the validators agree to do that if all the validators were to say hey the system program now allows you to Min
- [00:32:28](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1948) ➜ Soul then we could make that change and suddenly the system program could do that but the validators will not agree to do that why would they this would be
- [00:32:39](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1959) ➜ bad for the network if anybody could mint Soul so they're not going to do that however they might agree that a more efficient token program is a really
- [00:32:50](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1970) ➜ good thing for the network therefore they might be willing to make that change and vote for yes I approve approve this so there will be a simd it
- [00:33:00](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1980) ➜ will get approved and then validators will upgrade to a version where token kek actually has a different implementation and that is consensus
- [00:33:08](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1988) ➜ breaking because from one Epoch to the next token kek will behave differently it will have different code I mean it will behave the same to the user and the
- [00:33:19](https://www.youtube.com/watch?v=n-ym1utpzhk?t=1999) ➜ deaths pretty much it will just you know not have debug messages anymore and be way more CU efficient and the only downside here is that this
- [00:33:30](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2010) ➜ implementation is not yet battle tested and might contain a bug it's more likely that P token has a bu than token kek because token kek has been around the SP
- [00:33:41](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2021) ➜ token implementation I mean the original token cake it has been around forever I mean in Solana terms and nothing was ever exploited so fine and if there was
- [00:33:52](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2032) ➜ a bug in P token that would be really bad because all of the tokens including usdc and let me show you um let's say it has quite some Supply what is that $9
- [00:34:09](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2049) ➜ billion wow and that guess what this account is owned by token cake if we check that we will see it is owned by token cake so anyway what was I so token
- [00:34:22](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2062) ➜ cake quite a big deal like most of the value on Solana is is held by this program so it would be really really bad if P token had a bug and we would change
- [00:34:36](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2076) ➜ the implementation so that's why they are super careful they're doing audits they're doing tests they're doing fuzzing and the good thing is it's not
- [00:34:44](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2084) ➜ that big of a program it's relatively simple from what it does so if enough eyes look at it and I'm also going to look at it some more and more people are
- [00:34:55](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2095) ➜ going to look at it you can also look at it if you want want to and eventually I guess validators will vote for updating the implementation they currently Target
- [00:35:05](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2105) ➜ Solana version 2.2 I think and with 2.2 going live it will be in one of the feature flags and the process is that it's always one
- [00:35:15](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2115) ➜ feature flag per Epoch so after a few epochs that feature flag will get activated and then at the epoch boundary we will change from the old token
- [00:35:25](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2125) ➜ program implementation to the new token program implementation which is p token but it's the same token program and that's how you update an immutable
- [00:35:35](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2135) ➜ program cuz nothing is really immutable because if the validators decide it's not immutable it's not immutable that's how powerful the validators are but
- [00:35:43](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2143) ➜ welcome to a distributed system like that where the power is by the people running consensus that's why it would be bad if one or two of them had all the
- [00:35:54](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2154) ➜ soul cuz then they could do whatever just another reminder why it does matter where you stake and where you put your soul and who you trust because basically
- [00:36:04](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2164) ➜ validators they got some power just saying anyway so yeah I hope that you got a good introduction to P token why we need it why it's so cool I hope you
- [00:36:14](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2174) ➜ understand how P token will become token kek and to reiterate what that means for you as a de well not much honestly you don't need
- [00:36:25](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2185) ➜ to change your programs if you CPI into token kek everything should work the same the only thing that changes is cu so if you expect the instruction to take
- [00:36:37](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2197) ➜ quite some CU and you want to be efficient at the point where the feature flag gets activated you can lower this limit to the one from P token you'll
- [00:36:46](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2206) ➜ just have to simulate them again and see what the limits are now and another thing that will change is logs will be different I don't think they will keepy
- [00:36:57](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2217) ➜ all the same messages they might I don't know in the version that I have here the login got disabled I don't know if they will keep it or not we will see but
- [00:37:07](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2227) ➜ potentially there won't be logs anymore so if your script relies on on you know those outputs here which I don't think it does and it really shouldn't if your
- [00:37:18](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2238) ➜ logic depends on some log data even if it's you know this stuff I would prefer to get it from the instruction data directly but anyway I don't think
- [00:37:28](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2248) ➜ anybody checks for that but I also don't know everybody so some people might actually look for those things in the logs and that might just disappear those
- [00:37:38](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2258) ➜ things that might just disappear but that's the only real change that you're going to encounter otherwise it's just going to be more efficient yeah I mean
- [00:37:47](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2267) ➜ I'm looking forward to this change this got I again it won't feel like anything it will be the exact same right but it's going to be just so much more efficient
- [00:37:57](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2277) ➜ and we will have more block space for other things yeah optimizing your programs guys that is something that we need to do now as well on Solana
- [00:38:07](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2287) ➜ remember the days where we were looking at the evm guys and how they optimize their program and we're like it doesn't matter on Solana yeah
- [00:38:16](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2296) ➜ well times have changed and I expected that to happen as well I I I said it back then time will come where we need to take care of that as well and time
- [00:38:26](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2306) ➜ has come and the people from ANA are taking care of that and the token program really is such a heavily used program that it totally makes sense to
- [00:38:35](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2315) ➜ update with a new implementation and that's what P token is so have a look at it let us know what you think of it let me know what you think of it better on
- [00:38:43](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2323) ➜ Twitter I might disable comments because I get so much spam here on YouTube but uh you can still leave me a like and you can go watch those videos and you can
- [00:38:52](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2332) ➜ also subscribe if you haven't done that yet it's time and I will see you in one of my next vide videos there so many cool stuff happening on salana and I
- [00:39:01](https://www.youtube.com/watch?v=n-ym1utpzhk?t=2341) ➜ want to keep you up to date yeah till next time bye-bye
