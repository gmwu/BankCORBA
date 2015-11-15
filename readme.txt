To start the KTH Bank Example: 
tnameserv -ORBInitialPort 1050



To map bank.idl to Java: 

module bankidl {
    interface Account {
        readonly attribute float balance;
        exception rejected { string reason; };
        void deposit(in float value) raises( rejected);
        void withdraw(in float value) raises( rejected);
    };

    interface Bank {
        exception rejected { string reason; };
        Account newAccount( in string name) raises( rejected);
        Account getAccount ( in string name);
        boolean deleteAccount( in string acc );
    };
};









To start the ordb: 
orbd -ORBInitialPort 1050 -ORBInitialHost localhost&


To run the app: 
java CalcyServer -ORBInitialPort 1050 -ORBInitialHost localhost&
java CalcyClient -ORBInitialPort 1050 -ORBInitialHost localhost&

Needs to be in that working directory of the app.

