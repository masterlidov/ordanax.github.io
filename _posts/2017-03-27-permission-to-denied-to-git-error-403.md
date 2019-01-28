---
title: 'Git ошибка remote: Permission to user/repo denied to user/other-repo'
date: 2017-03-27 07:03:00 Z
permalink: "/permission-to-denied-to-git-error-403"
categories:
- useful
tags:
- git
- github
description: 'Варианты решения ошибки Git remote: Permission to denied to fatal: unable
  to access The requested URL returned error: 403.'
header: 'Решение ошибки remote: Permission to user/repo denied to user/other-repo.
  fatal: unable to access user/repo: The requested URL returned error: 403'
layout: post
---

В данном уроке рассмотрим варианты решения данной оишбки:

> **remote: Permission to user/repo denied to user/other-repo.**
> **fatal: unable to access user/repo: The requested URL returned error: 403** 

Возникает она чаще всего у новичков при попытке выполнить команду: 

`$ git push `

Пример ошибки на скриншоте ниже.

![git-permission-to-denied-to-error-403.jpg](/uploads/git-permission-to-denied-to-error-403.jpg)

Данная ошибка возникает довольно часто при работе с Git в терминале Windows. Суть ошибка довольно таки простая, но почему-то в интернете постоянно создаются темы с вопросом на данную тему и нет внятного ответа на русском языке.

Ошибка говорит нам о том, что мы пытаемся отправить данные в чужой репозиторий. И о том, что текущий пользователь Git не имеет прав для отправки данных в указанный в команде репозиторий.
<div>
<script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- htmlblog в тело статьи -->
<ins class="adsbygoogle"
     style="display:inline-block;width:600px;height:90px"
     data-ad-client="ca-pub-7700451254687983"
     data-ad-slot="6654417156"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script>
</div>
<br>
### Существует два способа решить данную ошибку:
<hr>
**Вариант 1. Дать текущему пользователю права для работы с репозиторием**

Данный способ подойдет, если вы являетесь владельцем обеих учетных записей указанных в ошибке. Необходимо зайти на GitHub под именем того пользователя, в чей репозиторий вы не можете отправить данные. В настройках репозитория указать необходимого соавтора. Ему на почту отправится приглашение, которое необходимо подтвердить, перейдя по ссылке в письме.

![github-repo-config.jpg](/uploads/github-repo-config.jpg)

После этого вы сможете работать с репозиторием как со своим и ошибка больше не появится.
<hr>
**Вариант 2. Назначить в системе текущим пользователем Git ту учетную запись, в которую не можете отправить данные**

Для этого необходимо перейти в Панель управления Windows. Выбрать отображение в виде категорий.

![win-panel.jpg](/uploads/win-panel.jpg)

Перейти в раздел "Учетные записи пользователей и семейная безопасность". Далее в раздел "Диспетчер учетных данных". В самом низу будет блок "Общие учетные данные". Нажмите в нем ссылку "Удаление из хранилища". 

![delete-git-config.jpg](/uploads/delete-git-config.jpg)

После этого при попытке выполнить команду:

`$ git push -u origin master`

Терминал запросит у вас пароль от учетной записи на Github в чей репозиторий вы пытаетесь отправить данные.

После ввода пароля система установит данного пользователя как основного и будет использовать его в дальнейшем при работе с Git.
<hr>
Надеюсь данный пост поможет вам решить ошибку, с которой я разбирался почти сутки.
