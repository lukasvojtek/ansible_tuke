```
// vytvorenie sifrovaneho suboru
ansible-vault create passwds.yml

// editacia
ansible-vault create passwds.yml

// sifrovanie
ansible-vault encrypt passwds.yml

// desifrovanie
ansible-vault decrypt passwds.yml

// spustenie playbooku s vyziadanim BECOME hesla
ansible-playbook main.yml -e @secret.yml --ask-become-pass

// spustenie playbooku s vyziadanim hesla na odsifrovanie @secret.yml runtime
ansible-playbook main.yml -e @secret.yml --ask-vault-pass
```

Cez `ansible.cfg` vieme definovat, odkial sa ma zobrat heslo pre odsifrovoanie suboru s heslami pouzitim:
```
vault_password_file = .vault_pass
```
kde obsah `.vault_pass` bude:
```
moje_tajne_heslo
```

t.j. v mojom pripade `test`
