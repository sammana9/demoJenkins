

pipeline{
agent any
parameters {

booleanParam(name:'check',defaultValue:'true',description:'checking the booleanvalue')
}

stages{
stage('test') {

script {

if(params.check)
{
echo 'value is true'
}
else
{
 echo 'value is false'
}


}

}
}
}
