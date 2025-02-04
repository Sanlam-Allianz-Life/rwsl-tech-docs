# Oracle DB

## DB Setup & Configuration

- Production DB hosted on `192.168.1.40`
- Oracle Entreprise manager hosted on [192.168.1.40:5500](http://192.168.1.40:5500)

## Schema

| **Schema Name**                                         | **Description** |
|---------------------------------------------------------|-----------------|
| [OLFSORDATA](../oracle/schemas/olfsordata/index.md)     | Ordinary Life   |
| [OLFSORCOMMOM](../oracle/schemas/olfsorcommon/index.md) |                 |
| [GRPLFDATA](../oracle/schemas/grplfdata/index.md)       | Group Life      |
| [OLGLDATA](../oracle/schemas/olgldata/index.md)         | General Ledger  |
| [EXT](../oracle/schemas/ext/index.md)                   | External        |
| [BNRVIE](../oracle/schemas/bnrvie/index.md)             | BNR             |

## Jobs

### Value Acquired

## Frequently Used Commands

### DB Start / Restart

- Login to the server using **PuTTY**
- Switch to oracle user

    ```cmd
    su - oracle
    ```

- Login as sysdba user

    ```cmd
    sqlplus / as sysdba
    ```

- Execute startup command

    ```cmd
    startup;
    ```

- In case of network errors, restart the Listner

    ```cmd
    lsnrctl start   
    ```

    Check listener status

    ```cmd
    lsnrctl status
    ```
