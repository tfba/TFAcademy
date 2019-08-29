"# TFAcademy" 

#Token 만들기

- 1. 트위터 링크로 faucet 신청하기.

https://www.rinkeby.io/#faucet 

- 2. truffle package 설치하기

https://www.trufflesuite.com/docs/truffle/quickstart

```
npm install -g truffle
mkdir mytoken
cd mytoken
truffle init
```

- 3. openzepplin 설치하기

`npm install zeppelin-solidity`

- 4. myToken 컨트랙트 작성

```
contract/mytoken.sol
migrations/2_deploy_mytoken.js
```


- 5. 컨트랙 빌드 / 디플로이

truffle.js (or truffle-config.js) 에 rinkeby config 넣기.

```
truffle deploy --network rinkeby
```

contract address 에서 explorer에서 token contract 확인하기.

- 6. explorer 에서 오너주소 / contract 주소 확인하기

https://rinkeby.etherscan.io/

- 7. MyetherWallet 에서 rinkeby network 선택하고, 토큰 확인하기.

- 8. 토큰 보내고 받기.

- 방법1) Truffle 에서 ABI 를 extract 하기 위해서, https://github.com/trustfarm-dev/truffle-export-abi 참조할것

- 방법2) ABI 만 간략하게 뽑고 싶을경우는 , 
build/contract/xxxx.json  에서 "abi" 섹션을 사용하면 된다.

https://medium.com/@piyopiyo/how-to-get-contract-abi-in-truffle-22d0c0457ceb 참조:
```
const fs = require('fs');
const contract = JSON.parse(fs.readFileSync('./build/contracts/ExampleSmartContract.json', 'utf8'));
console.log(JSON.stringify(contract.abi));
```
