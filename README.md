# TESTAPIAUTO
package apiauto;

import io.restassured.RestAssured;
import io.restassured.response.Response;
import io.restassured.specification.RequestSpecification;
import org.testng.annotations.Test;

import static org.testng.Assert.assertEquals;
import static org.testng.Assert.assertTrue;

public class SELESAI {
    private static RequestSpecification req;
    private static Response res;

    // Tes Positif: Uji API untuk respons yang benar dengan input yang benar
    @Test
    public void testPositiveScenario() {
        req = RestAssured.given()
                .header("Content-Type", "application/json")
                .header("Accept", "application/json")
                .header("app-id", "64dc4ca440e42010ace619a0");
        res = req.get("https://reqres.in/api/users/2");

        // Memeriksa kode status 200 OK
        assertEquals(res.getStatusCode(), 200);
        // Menambahkan lebih banyak asserstion sesuai kebutuhan
    }

    // Tes Negatif: Uji API untuk respons yang salah dengan input yang salah
    @Test
    public void testNegativeScenario() {
        req = RestAssured.given()
                .header("Content-Type", "application/json")
                .header("Accept", "application/json")
                .header("app-id", "64dc4ca440e42010ace619a0");
        res = req.get("https://reqres.in/api/users/1000"); // ID yang tidak valid

        // Memeriksa kode status 404 Not Found atau sesuai dengan kebutuhan
        assertTrue(res.getStatusCode() == 404 || res.getStatusCode() == 400);
        // Menambahkan lebih banyak asserstion sesuai kebutuhan
    }

    // Tes Batas: Uji API untuk edge cases yang berbeda
    @Test
    public void testBoundaryScenario() {
        req = RestAssured.given()
                .header("Content-Type", "application/json")
                .header("Accept", "application/json")
                .header("app-id", "64dc4ca440e42010ace619a0");
        res = req.get("https://reqres.in/api/users?page=1&per_page=1000"); // Meminta banyak data

        // Memeriksa kode status 200 OK
        assertEquals(res.getStatusCode(), 200);
        // Memeriksa apakah jumlah pengguna tidak melebihi batas (misalnya, 1000)
        assertTrue(res.jsonPath().getList("data").size() <= 1000);
        // Menambahkan lebih banyak asserstion sesuai kebutuhan
    }
}
