# kube-repo

server {
    listen   80;
    listen   [::]:80;
    listen   443 default_server ssl;

    server_name poc-nad.techmahindra.com;

    ssl_certificate        /home/ubuntu/cert.crt;
    ssl_certificate_key    /home/ubuntu/cert.key;


    if ($scheme = http) {
        return 301 https://$server_name$request_uri;
    }
}


$kubectl create configmap  --from-file=some-key=some-config.yaml -n some-namaespace
