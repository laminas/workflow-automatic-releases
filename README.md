# Laminas Reusuable Automatic Releases Workflow

> ## 🇷🇺 Русским гражданам
> 
> Мы, участники Laminas, родились и живем в разных странах. У многих из нас есть друзья, родственники и коллеги как в России, так и в Украине. Некоторые из нас родились в России. Некоторые из нас живут в России. У некоторых бабушки и дедушки сражались с фашистами во Второй мировой войне. Здесь никто не поддерживает фашизм.
> 
> У одного из нас есть украинская родственница, которая спаслась из дома вместе с сыном. Поезд задержался из-за бомбежки на дороге впереди. У нас есть друзья, которые прячутся в бомбоубежищах. Мы с тревогой ждем весточки от них после воздушных налетов, которые беспорядочно наносят удары и попадают по больницам, школам, детским садам и домам. Мы не берем это из каких-либо СМИ. Мы наблюдаем это напрямую.
> 
> Вы доверяете нам достаточно, чтоб использовать наши программы, и мы просим вас довериться нам вновь. Мы нуждаемся в помощи. Выходите и протестуйте против этой бесполезной войны. Остановите кровопролитие. Скажите "Нет войне!"
> 
> ## 🇺🇸 To Citizens of Russia
> 
> We at Laminas come from all over the world. Many of us have friends, family and colleagues in both Russia and Ukraine. Some of us were born in Russia. Some of us currently live in Russia. Some have grandparents who fought Nazis in World War II. Nobody here supports fascism.
> 
> One team member has a Ukrainian relative who fled her home with her son. The train was delayed due to bombing on the road ahead. We have friends who are hiding in bomb shelters. We anxiously follow up on them after the air raids, which indiscriminately fire at hospitals, schools, kindergartens and houses. We're not taking this from any media. These are our actual experiences.
> 
> You trust us enough to use our software. We ask that you trust us to say the truth on this. We need your help. Go out and protest this unnecessary war. Stop the bloodshed. Say "stop the war!"

This repository contains a reusable workflow describing the Laminas Project automatic releases process.


## Usage

To use the automatic releases workflow:

```yaml
# In a package repository, in the file .github/workflows/release-on-milestone-closed.yml:
name: "Automatic Releases"

on:
  milestone:
    types:
      - "closed"

jobs:
  release:
    uses: laminas/workflow-automatic-releases/.github/workflows/release-on-milestone-closed.yml@1.x
    secrets:
      GIT_AUTHOR_EMAIL: ${{ secrets.GIT_AUTHOR_EMAIL }}
      GIT_AUTHOR_NAME: ${{ secrets.GIT_AUTHOR_NAME }}
      ORGANIZATION_ADMIN_TOKEN: ${{ secrets.ORGANIZATION_ADMIN_TOKEN }}
      SIGNING_SECRET_KEY: ${{ secrets.SIGNING_SECRET_KEY }}
```

## Available references

GitHub recommends when using reusable workflows that you specify a reference to ensure stability.
This package defines a release branch per stable version, as well as tags.
Generally speaking, a release branch will only receive:

- Bugfixes
- New opt-in features (including optional inputs, and new outputs)

Since they will not receive backwards incompatible changes, you can pin to them.

We also provide tags.
Tags are immutable, and can be trusted without issue; however, your project will not benefit from updates without first changing the reference in your workflow.

### Current branches

- 1.x

### Tags

Please see the [releases page](/laminas/workflow-continuous-integration/releases) for a complete list.
