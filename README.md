# git-hooks-lab

```bash
# .git/hooks/commit-msg
NAME=$(git branch | grep '*' | sed 's/* //')
DESCRIPTION=$(git config branch."$NAME".description)

echo "[$NAME]"' '$(cat "$1") > "$1"
if [ -n "$DESCRIPTION" ]
then
   echo "" >> "$1"
   echo $DESCRIPTION >> "$1"
fi
```
