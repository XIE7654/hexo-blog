---
title: django-import-export
date: 2018-12-14 18:39:25
tags:
---

# 1.在项目中安装django-import-export
```
pip install django-import-export
```

# 2.在setting的INSTALLED_APPS中添加django-import-export
```
INSTALLED_APPS = [
    # pg 是创建的app
    'pg'，
    'import_export'，
]
```
# 3.models.py的模型
```
class Area(models.Model):
    name = models.CharField('名字', max_length=10)

    def __str__(self):
        return self.name

```

# 4.定制Resource:
```
from django.contrib import admin
from ask.models import Area
from import_export import resources
from import_export.admin import ImportExportModelAdmin

class Employee_Resource(resources.ModelResource):
    def get_export_headers(self):
        # 是你想要的导出头部标题headers
        return ['名字']

    class Meta:
        model = models.Employee
        fields = ('id', 'name',)
        export_order = ('id', 'name',)

class AreaAdmin(ImportExportModelAdmin):
    list_display = ('id', 'name')
    list_filter = ('name')
    search_fields = ('name')
    resource_class = Employee_Resource


admin.site.register(Area, AreaAdmin)
```
