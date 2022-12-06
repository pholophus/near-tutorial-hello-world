Hello NEAR
==========

**Hello NEAR!** is a friendly decentralized App that stores a greeting message. It is one of the simplest smart contracts you can create in NEAR, and the perfect gateway to introduce yourself in the world of smart contracts.

![img](https://docs.near.org/assets/images/hello-near-banner-af016d03e81a65653c9230b95a05fe4a.png)

* * *

Starting Hello NEAR[​](#starting-hello-near "Direct link to heading")
---------------------------------------------------------------------

You have two options to start Hello NEAR:

1.  **Recommended:** use the app through Gitpod (a web-based interactive environment)
2.  Start the project locally by using `create-near-app`, our node-based utility.

#### Gitpod[​](#gitpod "Direct link to heading")

Hello NEAR is available in gitpod. When selecting one, a new tab will open in your browser with a web-based IDE. Give it a minute to compile and deploy the contract, and then a frontend will pop-up for you to interact with the app (make sure the pop-up window is not blocked).

🌐 JavaScript

🦀 Rust

🚀 AssemblyScript

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/near-examples/hello-near-js.git)

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/near-examples/hello-near-rust.git)

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/near-examples/hello-near-as.git)

#### Create Near App (node)[​](#create-near-app-node "Direct link to heading")

Hello NEAR can be created locally with the help of `create-near-app`. Follow the snippet bellow to create a local project.

    npx create-near-app@latest

and follow the instructions that appear on the screen.

* * *

Interacting With Hello NEAR[​](#interacting-with-hello-near "Direct link to heading")
-------------------------------------------------------------------------------------

Go ahead and login with your NEAR account. If you don't have one, you will be able to create one in the moment. Once logged in, change the greeting and see how our Hello NEAR app greets you!

![img](/assets/images/hello-near-887a4eb29d41c071631cfe2fb9247bf1.png) _Frontend of Hello NEAR_

* * *

Structure of a dApp[​](#structure-of-a-dapp "Direct link to heading")
---------------------------------------------------------------------

Now that you understand what the dApp does, let us take a closer look to its structure:

1.  The frontend code lives in the `/frontend` folder.
2.  The smart contract code is in the `/contract` folder.

### Contract[​](#contract "Direct link to heading")

The contract presents 2 methods: `set_greeting` and `get_greeting`. The first one stores a `string` in the contract's parameter `greeting`, while the second one retrieves it. By default, the contract returns the message `"Hello"`.

*   🌐 JavaScript
*   🦀 Rust
*   🚀 AssemblyScript

contract/src/contract.ts

    loading...

[See full example on GitHub](https://github.com/near-examples/hello-near-js/blob/master/contract/src/contract.ts#L3-L18#)

contract/src/lib.rs

    loading...

[See full example on GitHub](https://github.com/near-examples/hello-near-rs/blob/main/contract/src/lib.rs#L23-L36#)

contract/assembly/index.ts

    loading...

[See full example on GitHub](https://github.com/near-examples/hello-near-as/blob/main/contract/assembly/index.ts#L9-L23#)

### Frontend[​](#frontend "Direct link to heading")

The frontend is composed by a single HTML file (`/index.html`). This file defines the components displayed in the screen.

The website's logic lives in `/assets/js/index.js`, which communicates with the contract through `/near-interface.js`. You will notice in `/assets/js/index.js` the following code:

*   🌐 JavaScript

frontend/index.js

    loading...

[See full example on GitHub](https://github.com/near-examples/hello-near-js/blob/master/frontend/index.js#L10-L21#)

It indicates our app, when it starts, to check if the user is already logged in and execute either `signedInFlow()` or `signedOutFlow()`.

* * *

Testing[​](#testing "Direct link to heading")
---------------------------------------------

When writing smart contracts it is very important to test all methods exhaustively. In this project you have two types of tests: unit and integration. Before digging in them, go ahead and perform the tests present in the dApp through the command `yarn test`.

### Unit test[​](#unit-test "Direct link to heading")

Unit tests check individual functions in the smart contract. Right now only rust implements unit testing.

*   🦀 Rust
*   🚀 AssemblyScript

contract/src/lib.rs

    loading...

[See full example on GitHub](https://github.com/near-examples/hello-near-rs/blob/main/contract/src/lib.rs#L46-L58#)

contract/assembly/\_\_tests\_\_/main.spec.ts

    loading...

[See full example on GitHub](https://github.com/near-examples/hello-near-as/blob/main/contract/assembly/__tests__/main.spec.ts#)

### Integration test[​](#integration-test "Direct link to heading")

Integration tests are generally written in javascript. They automatically deploy your contract and execute methods on it. In this way, integration tests simulate interactions from users in a realistic scenario. You will find the integration tests for `hello-near` in `integration-tests/`.

*   🌐 JavaScript

integration-tests/src/main.ava.ts

    loading...

[See full example on GitHub](https://github.com/near-examples/hello-near-js/blob/master/integration-tests/src/main.ava.ts#L32-L43#)

* * *

Moving Forward[​](#moving-forward "Direct link to heading")
-----------------------------------------------------------

A nice way to learn is by trying to expand the contract. Modify it so that you store one greeting message **per user**. For this, you will need to use knowledge from the [environment](/develop/contracts/environment/) and [storage](/develop/contracts/storage) sections. You can also use the [guest book](/tutorials/examples/guest-book) example, since it does something similar.
