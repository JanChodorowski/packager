# available clis for later inspiration

- create-medusa-app
- create-turbo

# ARTICLE

## 1.Context

### What was the background or situation leading to the problem? (Briefly explain the scenario or project phase when the issue occurred.)

We are developing nimara ecommerce platform that should be easy and rapid to set up

## 2. Problem

### What specific problem did you encounter? (Clearly define the issue.)

- there is no central point of information on what packages in what versions are used, any text documentation, if it exists, quicky gets out of sync and is additional overhead to maintain

- there are multiple environments - when developing demo and prod we loose track of environments

## 3. Why Was It Challenging?

### What made resolving this problem difficult or unique? (Highlight technical, operational, or situational constraints.)

- we want to deploy example storefronts with private integrations but do not share code only for open source solutions

- nimara ecommerce storefront already uses turborepo and still needs to be a part of a bigger monorepo

- we want to be able to modify dependant packages within one repo and commit changes from one place to multiple projects at the same time

- most of the components are open source but there are a few integrations that are either client-specific or are closed source and licensed

- we have parts that are both TS and python, and we don't want to enforce anyone to install any tools for setup and testing

## 4 Solution

### What steps did you take to address the problem? (List actions or technical fixes in bullet points.)

#### PART 1 handling storefront's turborepo packages

#### PART 2 handling external applications

#### ? PART 3 putting it all toghether

#### PART 4 setting up procedure - agile approach

#### PART 5 building cli to automate tested procedure

## 5 Outcome

### What was the result of your efforts?(State the measurable or qualitative impact of the solution.

### Example top level yml configuration file

```yml
components:
  nimara-storefront:
    location: ./turborepo
    search:
      provider: algolia
      depends_on:
        integration: algolia-ts@0.0.1
        location: ./algolia-ts

  algolia-ts:
    location: ./algolia-ts

  private-integration:
    repo: ht
```

## 6. Lessons Learned or Tips

### What did you learn, or what advice can you share?(Include insights for others facing similar challenges.)
