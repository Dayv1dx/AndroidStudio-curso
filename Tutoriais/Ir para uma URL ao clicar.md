~~~ java
private void goToURL(String s) {
    
        Uri url = Uri.parse(s);
        startActivity(new Intent(Intent.ACTION_VIEW, url));
    }

gitDayvid.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View v) {
                    goToURL("https://github.com/Dayv1dx");}});
~~~ 