# commit-convention-sample

--- 

## Commit Message Formats

### Default
<pre>
<code>
<b><a href="#type">&lt;type&gt;</a></b> (<b><a href="#scope">&lt;optional scope&gt;<b>): <b><a href="#subject">&lt;subject&gt;</a></b>

<b><a href="#body">&lt;body(optional)&gt;</a></b>

<b><a href="#footer">&lt;footer(optional)&gt;</a></b>
</code>
</pre>


### initail commit
```
init: init
```
---

### type
- `feat`: 새로운 기능을 추가할 때 사용합니다.
```
feat: add user authentication
feat(auth): add user login functionality
```
- `fix`: 버그를 수정할 때 사용합니다.
```
fix: correct user data parsing issue
fix(api): correct user data parsing issue
```
- `style`: 코드의 의미에 영향을 주지 않는 변경사항일 때 사용합니다. (포매팅, 세미콜론 추가, 공백 수정 등등.. )
```
style(ui): update button styles
```
- `refactor`: 기능 변경 없이 코드 리팩토링을 할 때 사용합니다.
```
refactor(db): optimize query for user retrieval
```
- `perf`: 성능을 향상시키는 코드 변경 시 사용합니다.
```
perf: improve data fetching performance
```
- `build`: 빌드 시스템 또는 외부 종속성에 영향을 미치는 변경 사항에 해당될 떄 사용합니다.
```
build: update webpack configuration
build: update java version
```
- `test`: 테스트 추가 또는 기존 테스트 코드 수정 시 사용합니다.
```
test: add unit tests for login component
```
- `docs`: 문서만 변경할 때 사용합니다. readme 와 같은 파일 수정 시 사용합니다.
```
docs: update installation instructions
docs(readme): add comment about commit convention
```
- `ci`: CI 구성 파일 및 스트립트 변경 시 사용합니다.
```
ci: update TravisCI configuration to run tests
```
- `chore`: 위에 해당하지 않은 기타 내용에 해당될 때 사용합니다.
```
chore: update npm dependencies
```

### scope
- scope 부분은 `optional` 입니다.
- 어떤 모듈이나 기능에 대한 변경 범위를 나타냅니다.
- 프로젝트에 따라 범위가 다릅니다.
- ex)
	- 모듈 또는 패키지 ) auth, api, db, ui ...
	- 기능 또는 컴포넌트 ) login, signup, navbar ...
  - 파일 또는 디렉토리 ) readme, env, example.properties..
 
### subject
- 50자 이내로 작성합니다.
- 소문자로 시작하며 끝에 마침표를 사용하지 않습니다.
- 작성 시 현재 시제를 사용합니다 ex) change, add | not "changes" nor "changed", "added" ...

--- 

### body
- body 부분은 `optional` 입니다.
- 변경 사항을 더 자세하게 제공하기 위해 작성합니다. 변경 이유와 내용이 포함될 수 있습니다.
- 각 줄은 72자 이내로 작성하며, 필요 시 여러 단락으로 나누어 작성합니다.
- `무엇`을 `왜` 진행했는지에 대해 작성하며, 변경 사항에 대해서는 `현재 시제`를 사용합니다.

--- 

### footer
- footer 부분은 `optional` 입니다.
- 이슈 트래커 ID를 참조하거나, 브레이킹 체인지(BREAKING CHANGE)와 같은 추가 정보를 제공할 때 사용합니다.
	- 기존 기능과의 호환성이 깨지는 변경 사항을 설명
  - 해당 변경에 의해 다른 코드가 깨지거나 변경해야 하는 경우 ex) `/api/v1` -> `/api/v2`, `user` to `users`
- 푸터의 각 항목은 새로운 줄에서 시작합니다.
- 푸터 토큰 작성 시 글자 사이의 공백 대신에 `-`를 사용해야 합니다. (BREAKING CHANGE 제외)

#### `footer keywords`
- Fixes: 버그 수정, 문제해결 :: issue가 자동으로 클로즈됩니다.
```
...
.
Fixes #10
```
- Resolves: 버그 수정 뿐만 아니라, 기능 추가, 개선, 기타 다양한 작업 :: issue가 자동으로 클로즈됩니다.
```
...
.
Resolves #11
```
- Refs: 특정 이슈를 참조합니다.
```
...
.
Fixes #12
Refs #10
```
- See also: 추가적으로 확인해야 하는 이슈를 참조합니다.
```
...
.
Fixes #13
See also #10, #11
```
- Co-authored-by: 공동 작업자의 정보를 추가할 때 사용합니다. 이는 주로 여러 명이 협력한 커밋에 사용됩니다.
```
...
.
Co-authored-by dash doe <sample@example.com>
```
- BREAKING CHANGE: 이 커밋이 주요 변경사항을 포함하고 있으며, 호환성에 영향을 미칠 수 있음을 나타냅니다.
```
...
.
BREAKING CHANGE The API endpoint /v1/users has been removed.
```
- Reviewed-by: 코드 리뷰를 수행한 사람을 명시할 때 사용합니다.
```
...
.
Reviewed-by name <email@email.com>
```
--- 

### examples

```
feat(auth): Add user login feature

Implemented user login functionality using JWT. This includes the login form, authentication service, and relevant routes.

Fixes #42
See also #33
Co-authored-by: exmaple <sample@gmail.com>
```
<br>

```
docs(README): Update installation instructions

Added detailed steps for setting up the project locally. Included instructions for installing dependencies and running the development server.
``` 
<br>

```
test: add example for login service

Closes #103
```
<br>

```
feat(auth): add user login feature (#42)

Implemented user login functionality using JWT. This includes the login form, authentication service, and relevant routes.

Fixes #42
```
<br>

```
fix(api): correct user data parsing issue (#43)

Fixed a bug where the user data was incorrectly parsed from the API response. Updated the parsing logic to handle edge cases.

Closes #43
```
<br>

```
refactor(auth): change login API endpoint (#89)

The login API endpoint has been changed from /api/v1/login to /api/v2/login. All clients must update their integrations accordingly.

BREAKING CHANGE: The login API endpoint has been changed.
```
---

## References
* [https://www.conventionalcommits.org/](https://gist.github.com/qoomon/5dfcdf8eec66a051ecd85625518cfd13#footer)
* [https://github.com/angular/angular/blob/master/CONTRIBUTING.md](https://www.conventionalcommits.org/en/v1.0.0/)
* [https://github.com/testcontainers/testcontainers-java](https://github.com/testcontainers/testcontainers-java)
