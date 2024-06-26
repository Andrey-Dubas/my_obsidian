
// generateJWT creates a signed JSON Web Token using a Google API Service Account.func generateJWT(saKeyfile, saEmail, audience string, expiryLength int64) (string, error) {        now := time.Now().Unix()        // Build the JWT payload.        jwt := &jws.ClaimSet{                Iat: now,                // expires after 'expiryLength' seconds.                Exp: now + expiryLength,                // Iss must match 'issuer' in the security configuration in your                // swagger spec (e.g. service account email). It can be any string.                Iss: saEmail,                // Aud must be either your Endpoints service name, or match the value                // specified as the 'x-google-audience' in the OpenAPI document.                Aud: audience,                // Sub and Email should match the service account's email address.                Sub:           saEmail,                PrivateClaims: map[string]interface{}{"email": saEmail},        }        jwsHeader := &jws.Header{                Algorithm: "RS256",                Typ:       "JWT",        }        // Extract the RSA private key from the service account keyfile.        
sa, err := ioutil.ReadFile(saKeyfile)    

conf, err := google.JWTConfigFromJSON(sa)       
block, _ := pem.Decode(conf.PrivateKey)        
parsedKey, err := x509.ParsePKCS8PrivateKey(block.Bytes)        
if err != nil {           
	return "", fmt.Errorf("private key parse error: %w", err)        
}        
rsaKey, ok := parsedKey.(*rsa.PrivateKey)        // Sign the JWT with the service account's private key.        
if !ok {            
		return "", errors.New("private key failed rsa.PrivateKey type assertion")
}
return jws.Encode(jwsHeader, jwt, rsaKey)}