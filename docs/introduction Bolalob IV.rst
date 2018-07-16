###############################
Introduction Bolalob IV
###############################

Code Sample I
==============

.. code:: html

    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">
        <title>Document</title>
    </head>
    <body>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil, nobis? Nisi quaerat quisquam repudiandae et non nam ipsa dolore quae. Minus laboriosam a cumque dolore aliquid voluptatibus vitae numquam tempora?
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Eius omnis, corporis fugiat aliquid asperiores veritatis impedit molestias molestiae dolores minima odio officiis. Eligendi optio perspiciatis magnam ut quia officia dignissimos.
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Recusandae officia sequi ratione minus accusamus, ipsa, tempora quos blanditiis facilis repudiandae corrupti nostrum, deserunt debitis porro quas possimus nobis consectetur vel.
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Autem perspiciatis laborum iste nesciunt nam consequuntur quaerat in optio eveniet iure facilis, id alias dolore! Mollitia natus facilis reiciendis tempore molestiae.
    </body>
    </html>

Code Sample II
==============

.. code:: javascript
    :linenos:
    :emphasize-lines: 3,5
    
    example_function {
        // The keyword "public" makes those variables
        // readable from outside.
        address public minter;
        mapping (address => uint) public balances;

        // Events allow light clients to react to
        // changes efficiently.
        event Sent(address from, address to, uint amount);

        // This is the constructor whose code is
        // run only when the contract is created.
        constructor() public {
            minter = msg.sender;
        }

        function mint(address receiver, uint amount) public {
            if (msg.sender != minter) return;
            balances[receiver] += amount;
        }

        function send(address receiver, uint amount) public {
            if (balances[msg.sender] < amount) return;
            balances[msg.sender] -= amount;
            balances[receiver] += amount;
            emit Sent(msg.sender, receiver, amount);
        }
    }