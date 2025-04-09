# get helm from the chart (azure)

helm registry login $ACR_NAME.azurecr.io --username $USER_NAME --password $PASSWORD

helm pull oci://$ACR_NAME.azurecr.io/helm/$HELM_NAME --version $HELM_VERSION

# push pack to the registry (azure)

az acr login -n $REGISTRY  

oras push $REGISTRY/spectro-packs/archive/$PACK-NAME:$PACK-VERSION $ARTIFACT.tar.gz
