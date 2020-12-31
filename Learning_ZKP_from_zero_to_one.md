ZKP (Zero knowledge proof) is an interesting technology to prove something without reveal it.
Here are some tips from new learners of ZKP with no backgroup of cryptography：
* Number theory and elliptic curve cryptography：see the book <Elliptic Curves Number Theory and Cryptography（second edition）>.

* Useful math software: sageMath, or Magma. There's an online edition for Magma [Magma Calculator](http://magma.maths.usyd.edu.au/calc/).

* Homomorphic encryption: allows mathematical operations on data to be carried out on cipher text, e.g.，$e(g^x,g^y)=e(g,g^{xy})$ with multiplicative homomorphic，$g^x\cdot g^y=g^{x+y}$ with additive homomorphic. Homomorphic encryption is uesful for verification without reveal the raw data.

* Pairing: has multiplicative homomorphic property, can be divided into eta pairing, ate pairing, weil pairing, tate pairing, etc. If you want to know more about pairing, read  Craig Costello's <[Pairings for beginners](http://www.craigcostello.com.au/pairings/PairingsForBeginners.pdf)>, which provides many useful Magma codes for easy understanding.

* Commitment: read <[From Zero (Knowledge) to Bulletproof](https://github.com/AdamISZ/from0k2bp)> or my blog  [椭圆曲线形式下的Pedersen commitment——vector commitment和polynomial commitment](https://blog.csdn.net/mutourend/article/details/97012468). The Pedersen commitment has additive homomorphic property.

* Group: pairing-friendly group, unknown order group, known order group, etc.

* Cryptography computational assumption: the assumption is usually a mathematical problem that is hard to solve. The main computational assumptions in cryptography: discrete logarithm problem、factoring、pairing、lattice, etc.

* Program language: C++, Rust, Go, Python, Haskell, etc. Many recent papers about ZKP are realized with Rust. Rust is designed for performance and safety, especially safe concurrency, and achieves memory safety without garbage collection. If you want to code for ZKP, Rust is worth learning.

* ZKP repo: [Awesome zero knowledge proofs (zkp)](https://github.com/matter-labs/awesome-zero-knowledge-proofs) lists almost all new research about ZKP, choose the one you are interested in.

* Roles in ZKP:

Prover: the one know the secret.

Verifier: don't know the secret, but want to verify that Prover DO know the secret.

An example:

-- public instance: $y,g$ (known both by the Prover and Verifier)

-- witness: $x$ (secret info, only known by the Prover)

-- relation: $y=g^x$ (the relation that Verifier want to check, or the relation that Prover want to prove)

Can be done with sigma protocol (whose main idea is "commit-and-prove"). See my blog [基于Sigma protocol实现的零知识证明protocol集锦](https://blog.csdn.net/mutourend/article/details/106391126) for more info.

* ZKP application:

confidential transaction in Monero/ZCash；

storage proof in Filecoin;

multi-party computation;

delagete computation;

backlist/whitelist access control;

privacy computation, etc.

