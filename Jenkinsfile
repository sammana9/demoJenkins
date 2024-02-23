pipeline{
agent any
stages{
stage('userfetch'){
steps{

wrap([$class:'BuildUser']){
 echo "username: ${BUILD_USER}"
}

}
}
}
}
