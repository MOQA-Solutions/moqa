
# What is this

**Moqa** is a **Full Chat Server** and **Message Broker** that can offer many **Features**.<br>
The **Current Server** was designed to work as Frontend Server in association with **Moqabase Backend Server**
but you can *customize* it to work **Anywhere & Anyway**.<br>
You can check **All Moqa's Features** [here](https://github.com/MOQA-Solutions/moqa/blob/master/docs/moqa_guide.asciidoc), for more details and informations you should read **Source Code**.<br>

# Installation

- Actually, this Server does not support **Horizontal Scale**, all what we have is **One Server**, but this
will be my next step if you liked the work.<br>
- First, you should set your **Frontend Node** in **All your Backend Nodes** which run **Moqabase** as it
was described in **Moqabase Application**.<br>
- Next, you should **edit** both `moqa:partition_to_node/1` and `moqa:node_to_partition/1` functions as
your **Backend Configuration**, this was described in **Moqabase Application**.<br>
- Now you should **edit** `moqa.app` for 2 reasons :
  - To **edit Start Argument** which represents the **Number of Backend Partitions** (`mnesia` tables).<br>
    - The Number of Backend Partitions = The Number of Backend Nodes
    - You should read **Moqabase** Description for more informations.
  - To **edit** the **Port Number** and the **Number of Acceptors** of TCP Connections.
- After that, you can start **Moqa** Server on your Node :
```
rebar3 shell --sname somenode@somehost
```
When **Moqa Application** is running, you can use `moqa_interface.erl` to interact with the Application.<br>
You can check [here](https://github.com/moqa/blob/master/docs/moqa_interface.asciidoc) a full description of
`moqa_interface.erl`'s Functions.

   


