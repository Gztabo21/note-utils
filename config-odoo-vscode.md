## Configuration de vscode para usar con odoo
```
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Python: odoo",
            "type": "python",
            "request": "launch",
            "program": "${workspaceFolder}/odoo-bin",
            "args": [
                "--config=${workspaceFolder}/odoo.conf",
                "--update=tka_configuration_vehicle_overhauls"
            ],
            "console":"integratedTerminal",
        }
    ]
}
```