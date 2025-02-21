### Users

```powershell
net user /domain # Print users in the domain
```

```powershell
net user jeffadmin /domain # Inspect specific user in the domain
```

```powershell
net accounts # Get account policy
```

### Groups

Default groups: https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/understand-security-groups

```powershell
net group /domain # Print groups in the domain
```

```powershell
net group 'Sales Department' /domain # Inspect specific group in the domain
```

```powershell
net group "Management Department" stephanie /add /domain # Add user to a specific group in the domain
```

```powershell
net group "Management Department" stephanie /del /domain # Delete user to a specific group in the domain
```

