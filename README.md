# This is a extension for djangorestframework

## extend some mixins for bussiness development:
### views
- provide default action for CRUD: DefaultDestroyModelMixin, DefaultCreateModelMixin, DefaultRetrieveModelMixin, DefaultUpdateModelMixin
- batch delete: DefaultDestroyManyModelMixin
- seperate get method into retrieve and list: DefaultRetrieveModelMixin, DefaultListModelMixin
### communication
- remote access(http): RemoteAccessMixin

### how to use
- pip install requirements
- define your bussiness model and add CRUD mixin action as you want, keep 'GenericViewSet' is the last one of father-classes:

class XXXXXXXViewSet(mixins.DefaultCreateModelMixin,
                     mixins.DefaultRetrieveModelMixin,
                     mixins.DefaultUpdateModelMixin,
                     mixins.DefaultDestroyModelMixin,
                     mixins.DefaultDestroyManyModelMixin,
                     mixins.DefaultListModelMixin,
                     viewsets.GenericViewSet
                     ):
    """ XXXXViewSets """
    pass
