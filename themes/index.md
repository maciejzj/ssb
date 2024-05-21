# Header 1
## Header 2
### Header 3
#### Header 4
##### Header 5

* Bullet point 1
* Bulet point 2
* Bullet point 3

1. Ordered list first
2. Ordered list second
3. Ordered list third

A [link](https://maciejzj.xyz) to a website.

| Column 1 | Column 2 |
| -------- | -------- |
| Value 1  | Row 1    |
| Value 2  | Row 2    |
| Value 3  | Row 3    |

> A quote block.

A piece of *emph* text.

A piece of **strong** text.

![An image](https://api.culture.pl/sites/default/files/styles/260_auto_aspect/public/images/imported/sztuki%20wizualne/portrety/Jarema_mari/jerema_mairia_rolke_ag.jpg?itok=K7cmrkcF)

A ruler separating text.

---

Preformatted code/verbatim:

```
git filter-branch --env-filter '
WRONG_EMAIL="<WRONG_EMAIL>"
NEW_NAME="<NEW_NAME>"
NEW_EMAIL="<NEW_EMAIL>"

if [ "$GIT_COMMITTER_EMAIL" = "$WRONG_EMAIL" ]
then
    export GIT_COMMITTER_NAME="$NEW_NAME"
    export GIT_COMMITTER_EMAIL="$NEW_EMAIL"
fi
if [ "$GIT_AUTHOR_EMAIL" = "$WRONG_EMAIL" ]
then
    export GIT_AUTHOR_NAME="$NEW_NAME"
    export GIT_AUTHOR_EMAIL="$NEW_EMAIL"
fi
' --tag-name-filter cat -- --branches --tags
```
