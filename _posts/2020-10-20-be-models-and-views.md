---
layout: post
title: BE - Models and ViewSets
tags: phase-3 phase-3-be
---

Today, we talked through the models for your eCards app and talked through how to build ViewSets and custom permissions. We also talked through the proposed views you'll need for your app and how you might approach them.

Some of the topics we referenced along the way:

- choosing how to model our data based on business cases
- filtering models based off fields in their relationships
- using GET params to change your queryset in a view or viewset
- using `perform_create` in a ViewSet to add more behavior to object creation; specifically, this is to add a user object to a model

Some of the resources we used were:

- [ModelViewSet](https://www.django-rest-framework.org/api-guide/viewsets/#modelviewset)
- [Custom permissions](https://www.django-rest-framework.org/api-guide/permissions/#custom-permissions)
- [Classy DRF](http://www.cdrf.co/)

