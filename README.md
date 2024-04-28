# Company details

This Solidity smart contract, Company, facilitates the management of company details including ID, name, status, and starting salary.

## Description

The contract includes:

* Struct: details structure to hold company details such as ID, name, status, and starting salary.
Functions:
- addCompanyName: Allows adding company details including ID, name, status, and starting salary. It ensures that the starting salary is at least $100,000 and that the ID is not zero.
- getName: Retrieves the name of the company.
## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., error.sol). Copy and paste the following code into the file:

```solidity
//SPDX-License-Identifier:MIT
pragma solidity ^0.8.0;

contract company{
    struct details{
        uint id;
        string name;
        string status;
        uint start_salary;
    }
    details company_details;

    function addCompanyName(uint _id, string memory _name, string memory _status,uint _salary) public {
        require(_salary>100000,"The minimum starting salary is $100000");
        if(_id<=0){
            revert("Company ID cannot be 0");
        }
        company_details=(details(_id,_name,_status,_salary));
    }

    function getName() public view returns(string memory){
        assert(company_details.id!=0 );
        return company_details.name;
    }
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile error.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "error" contract from the dropdown menu, and then click on the "Deploy" button.

You can add company name and get the name of the company.

## Authors

Metacrafter Chris  
@gmail.com


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
