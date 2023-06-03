<hr/>
<hr/>

<a name="readme-top"></a>

# InteractionControl Contract

<hr/>

# Combines different smart contracts to grant total control of your functions if desired. From who calls them to in which order and even with which inputs' values.

## 💽Testing and implementation example repo => [(click)](https://github.com/CarlosAlegreUr/InteractionControl-SmartContract-Testing) 💽

## 💽NPM repo => [(click)](https://www.npmjs.com/package/interaction-control-contract) 💽

<hr/>

If further elaboration or development please mention me in your work.

😉 https://github.com/CarlosAlegreUr 😉

<hr/>

## 🤖 General usecase explanation 🤖

InteractionControl can be used to have total control of your functions if desired.

From who calls them to in which order and even with which inputs' values.

<hr/>

## ✨ How to use ✨

1. Make your contract inherit InteractionControl and add the isAllowedInteraction()
   modifier in the functions you desire to fully control.

   The isAllowedInteraction() has 3 parameters:

   1.1 => function selector of the function where it's being applied:
   bytes4(keccak256(bytes("funcSignatureAsString")))

   1.2 => msg.sender => to know who is calling.

   1.3 => a unique identifier of the inputs and it's values:
   keccak256(abi.encode(\_newNumber))

   Btw it's essential you use abi.enconde() and not abi.encodePakced() because abi.encodePakced()
   can give the same output to different inputs.

2. Additionally you can override callAllowInputsFor() or and callAllowFuncCallsFor() if you please mixing this
   InteractionControl with, for example, other useful ones like Ownable or AccessControl contracts from [OpenZeppelin](https://docs.openzeppelin.com/contracts/4.x/access-control).

As InteractionControl inherits from [CallOrderControl.sol](https://github.com/CarlosAlegreUr/CallOrderControl-SmartContract-DesignPattern/blob/main/CallOrderControl.sol) and [InputControl.sol](https://github.com/CarlosAlegreUr/InputControl-SmartContract-DesignPattern/blob/main/InputControl.sol) you can use just their modifier directly in a function
if pleased.

Check a simple implemented example at [UseCaseContract.sol](https://github.com/CarlosAlegreUr/InteractionControl-SmartContract-Testing/blob/main/contracts/UseCaseContract.sol).

<hr/>

## 🎉 FUTURE IMPROVEMENTS 🎉

- Improve and review (static analysis, audit...) code's tests.
- Test in testnet.
- Finish testing localhost, errors and inconsistencies found in dependant packages.

<hr/>

<a name="realcase"></a>

## 📨 Contact 📨

Carlos Alegre Urquizú - calegreu@gmail.com

<hr/>

## ☕ Buy me a CryptoCoffee ☕

Buy me a crypto coffe in ETH, MATIC or BNB ☕🧐☕
(or tokens if you please :p )

0x2365bf29236757bcfD141Fdb5C9318183716d866

<hr/>

## 📜 License 📜

Distributed under the MIT License. See [LICENSE](https://github.com/CarlosAlegreUr/InteractionControl-SmartContract-DesignPattern/blob/main/LICENSE) in the repository for more information.
