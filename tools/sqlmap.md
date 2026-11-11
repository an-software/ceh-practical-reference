# sqlmap

Priority writeup tool. Purpose: SQL injection assessment and narrowly scoped lab database enumeration.

## Basic workflow

1. Capture a complete current lab request into ignored `evidence/request.txt`.
2. Select the suspected parameter and validate the injection finding.
3. Enumerate only the schema/table/columns required by the lab; record the minimum proof.

## Example

```bash
sqlmap -r evidence/request.txt -p id --dbs
sqlmap -r evidence/request.txt -p id -D labdb --tables
sqlmap -r evidence/request.txt -p id -D labdb -T lab_users --columns
```

## Troubleshooting

Expired sessions and dynamic pages can defeat comparisons. Use `-D`, `-T`, `-C` with exact discovered names. Avoid putting `--dbs` after an unquoted shell semicolon. Database injection does not automatically permit OS command execution.

Related: [web testing](../topics/web-testing.md). Source: [SQLmap usage](https://github.com/sqlmapproject/sqlmap/wiki/Usage).

