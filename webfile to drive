function downloadFile(fileURL,folder) {
  
  var fileName = "";
  var fileSize = 0;
  
  var response = UrlFetchApp.fetch(fileURL, {muteHttpExceptions: true});
  var rc = response.getResponseCode();
  
  if (rc == 200) {
    var fileBlob = response.getBlob()
    var folder = DocsList.getFolder(folder);
    if (folder != null) {
      var file = folder.createFile(fileBlob);
      fileName = file.getName();
      fileSize = file.getSize();
    }
  }
    
  var fileInfo = { "rc":rc, "fileName":fileName, "fileSize":fileSize };
  return fileInfo;
}
