# cgcx-pre-sale
Smartcontract for cgcx pre-sale


# Not ready for production or public release 

# This contract has been written in test-driven development using Truffle framework and Solidity Language 

# Requirements for setting up environment 

 > Node.js 8.0+ 
 > Truffle 4.0+
 > npm 4.0+
 
 # Steps for Testing & Verifying
 
 S1 : Clone this repo or download this to local folder 
 S2 : truffle test 
 
 If everything was Success you will get an output like this : 
 
 
 Deploy CgcxPreSale { target: '0xa3d736079d6bf7c14a96ab3ad131c349ceaf141e',
  endDate: 1518105600,
  minContribution: 0.1,
  minCap: 100,
  maxCap: 200 }
target= 0xa3d736079d6bf7c14a96ab3ad131c349ceaf141e
endDate= 1518105600
minContribution= 100000000000000000
minCap= 100000000000000000000
maxCap= 200000000000000000000


  Contract: CgcxPreSale
    ✓ should properly set the values from the constructor (144ms)
    Public functions
      apply
        ✓ should not work after end (128ms)
        ✓ should fail if msg.value below minContrib (116ms)
        ✓ should fail if above maxCap (131ms)
        ✓ should fail if address already applied (199ms)
        ✓ should add application from the user and emit a PendingApplication event (211ms)
        ✓ should accept application that exceeds the max cap if all accepted (225ms)
      withdraw
        ✓ is only callable by owner (101ms)
        ✓ can withdraw only if minCap is reached (275ms)
        ✓ updates withdrawn property (486ms)
        ✓ can only withdraw what is available and not already withdrawn (477ms)
        ✓ transfer the funds to the target (761ms)
        ✓ emits a Withdrawn event (562ms)
    Restricted functions
      reject
        ✓ is only callable by owner (189ms)
        ✓ should reject the application, send Ether back to applicant and emit a RejectedApplication event (311ms)
        ✓ should update contributionPending and contributionRejected (383ms)
        ✓ should only work on pending applications (144ms)
      accept
        ✓ is only callable by owner (134ms)
        ✓ should accept the application and emit an AcceptedApplication event (410ms)
        ✓ should update contributionPending and contributionAccepted (295ms)
        ✓ should only work on pending applications (118ms)
    Views
      getApplicants
        ✓ should return the application (372ms)
      getMaximumContributionPossible
        ✓ should return the maximum contribution in Ether (357ms)
    Maintenance functions
      failsafe
        ✓ should only be callable two months after this end (322ms)
        ✓ should only be callable by owner (551ms)
        ✓ should transfer ethereum to the target (499ms)
      changeOwner
        ✓ should only be callable by owner (106ms)
        ✓ should update the owner (130ms)
        ✓ should send a ContractUpdate event (103ms)
      changeTarget
        ✓ should only be callable by owner (98ms)
        ✓ should update the target (122ms)
        ✓ should send a ContractUpdate event (101ms)
      changeMinCap
        ✓ should only be callable by owner (98ms)
        ✓ should update the minCap (108ms)
        ✓ should send a ContractUpdate event (118ms)
      changeMaxCap
        ✓ should only be callable by owner (96ms)
        ✓ should update the maxCap (110ms)
        ✓ should send a ContractUpdate event (107ms)
      changeMinContribution
        ✓ should only be callable by owner (90ms)
        ✓ should update the minContribution (125ms)
        ✓ should send a ContractUpdate event (104ms)


  41 passing (10s)

