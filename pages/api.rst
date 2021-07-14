API Documentation
####################

About API
*********

* API has been made using go language and serves the purpose of connecting Blockchain with ebots in ROS.
* To make API available over internet we have used ngrok. Alternatively port forwarding can also be used.
* Rest API is used for both vaccine center and ebots to connect with Blockchain.
* Vaccine center used it to place an order.
* Ebots use it to identify the delivery to make in there respective areas.

To place order from Vaccine centers
************************************

.. code-block:: javascript

    placeorder = {
    "Orderby" : "hosf",
    "Warehouse" : "warehouse1",
    }
    r = requests.post('http://localhost:8081/createList', json=placeorder)
    print(r.json())

To check Order from ebots
**************************

.. code-block:: javascript

    name = {
    'botname':'bot3'
    }
    r = requests.post('http://localhost:8081/checkYourOrder', data=name)
    print(r.json())

To change the delivery status after completion
**********************************************

.. code-block:: javascript

    r = requests.post('http://localhost:8081/ordererCompleted', data={'orderid':'orderlist2'})
    print(r.json())

.. note::
    Backend URL used here is ``http://localhost:8081`` replace it with URL of your server.

Challanges faced
****************

* One of the biggest problems with building the blockchain based rest api was we didn’t have any sources to learn so we had to experiment everything and had to build everything from scratch.

..
    * Other issues with it was we needed to access it again and again which increases the transaction time to over come that we had to convert it into a global variable so the files were only access only when it was required.

* We had to pass everything in string format and even decode the incoming data in string irrespective of the defined data structure in the blockchain.


